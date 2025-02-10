The thesis is about getting computer programs from one machine to another, and having them still work when they get there. This is the problem of *software deployment*.

 The development of principles and tools for the deployment process has largely been relegated to industry, system administrators, and Unix hackers. This has resulted in a large number of often *ad hoc* tools that typically automate manual practices but do not address fundamental issues in a systematic and disciplined way

This thesis describes a system for software development called *Nix* that addresses many of the problems that plague existing deployment systems.

## Software Deployment
Software deployment is the problem of managing the distribution of software to end-user machines.

The software works on the developers machine, the challenge is to make sure the software works the same on the end-user machines. This will be informally referred to as *correct deployment*: given identical inputs, the software should behave the same on and end-user machine as on the developer machine.

In theory this is simple, if the software consists of a set of files then deployment should be a simple matter of *copying* those to the target machine. In practice, deployment turns out to be much harder. This has a number of causes that fall into two broad categories: *environment issues* and *manageability issues*.

**Environment issues.** The first category is about correctness. The software might make all sorts of demands about the *environment* in which it executes. If any environmental characteristics do not hold, there is a possibility that software does not work the same as it did on the developer machine. Some concrete issues:

- A software component is almost never self-contained; rather, it depends on other components to do some work on its behalf. These are its *dependencies*. For correct deployment, it's necessary that all dependencies are identified.
- To build a component in the first place we need certain dependencies (such as compilers), and these need not be the same as runtime dependencies, although there may be some overlap. 
- More examples in the PhD thesis

We have two problems in deployment: We must *identify* what our component's requirements on the environment are, and we must *realize* those requirements in the target environment. Realization might consist of installing dependencies, creating or modifying configuration files, etc.

**Manageability issues.** The second category is about our ability to manage the deployment process. There are all kinds of operations that we need to be able to perform, such as packaging, transferring, installing, upgrading, uninstalling, and answering various queries; i.e., we have to be able to support the evolution of a software system. For example:
- When uninstalling a component we have to know what steps to take to safely undo the installation.
- When we preform a component upgrade, we should be careful not to overwrite any part of any component that might induce a failure in another part of the system. This is the well known *DLL hell*.
- More examples in the paper


## The state of the art
Having seen some of the issues in the field of software deployment, lets look at some representative deployment tools.

Package management is the perennial problem in the Unix community. Entire operating system distributions rise and fall on the basis of their deployment qualities.

Unix systems have traditionally insisted on storing components in global namespaces in the file system such as the /usr/bin directory. This makes management tools indispensable. (This is the reason Nix doesn't adhere to the linux FHS).

**RPM.** The Red Hat Package manager is a low-level deployment tool. A software component is deployed by packaging it into an RPM package, which is an archive file that consists of the files that constitute the component, and some meta-information about the package. This includes a specification of the dependencies of the packages, and other things. 

RPM maintains a cryptographic hash of the contents of each file as it existed at installation time. Thus, users can verify that files have not been tampered with. 

RPM maintains the integrity of installed packages with respect to the dependency requirements. Similarly, RPM doesn't allow two packages that contain files with equal path names to exist simultaneously in the system. In general, this means *we cannot have multiple versions of the same component installed simultaneously*.

A fundamental problem of RPM and essentially all general package management systems is that it cannot reliably determine the correctness of dependency specifications. If you forget to specify a dependency in the spec file, when the developer builds and tests the RPM Package, the component will probably work because the developer has the dependency installed, but when deployed to clients, the component will work if they happen to have the dependency installed, but if not, the component may fail mysteriously.

It is intrinsically hard to validate dependency specifications. Related to the inability to validate dependency specifications, dependencies tend to be *inexact*. Consider xhello, xhello requires that a component named hello is present, but it makes no requirements of the actual properties or interfaces of that component. The dependency specification is *nominal* (determined by name only), not by *contract* (requiring the dependency has certain properties).

A more subtle problem in RPM is that it has the property of *destructive upgrading*, which means that components are upgraded by overwriting the files of the old versions with those of the new one. This gives rise to a temporal inconsistency in the system: there is a time window in which we have some of the files of the old version, and some of the new version. This means upgrading is not *atomic*.

**Source deployment models.**  Several operating system distributions deploy packages not in binary form but in source form. This allows for greater flexibility by allowing users to make specific build time configuration choices.

An obvious downside to source deployment is its rather considerable resource consumption.

## Motivation
Existing deployment systems have some or all of the following problems:
- Dependency specifications are not validated, leading to incomplete deployment.
- Dependency specifications are inexact.
- It isn't possible to deploy multiple versions of a component side-by-side.
- Components can interfere with each other.
- It isn't possible to roll back to previous configurations.
- Upgrade actions aren't atomic.
- Applications must be monolithic, i.e., they must statically contain all their dependencies.
- Deployment actions can only be performed by administrators.
- There is no link between binaries and the sources and build processes that built them.
- The system supports either source deployment or binary deployment, but not both; or it supports both but in a non-unified way.
- It is difficult to adapt components.
- Component composition is manual.
- The component framework is narrowly restricted to components written in a specific programming language or framework.
- The system depends on non-portable techniques.

## The Nix deployment system
The *Nix deployment system* overcomes the limitations of deployment tools described above. The main idea of the Nix approach is to store software components in isolation from each other in a central component store, under path names that contain cryptographic hashes of all inputs involved in building the component, such as /nix/store/rwmfbhb2znwp...-firefox-1.0.4. This prevents undeclared dependencies and enables support for side-by-side existence of component versions and variants.

## Contributions
The main contribution here is the deployment of a *purely [[Monads for functional programming| functional]] deployment model*, which we implemented in the Nix system. A binary component is uniquely defined by the declared inputs used to build the component. This enables arbitrary component instances to exist side by side. The contributions of this thesis are the following:
- The cryptographic hashing scheme used by the Nix component store prevents undeclared dependencies, giving us complete deployment. Furthermore it provides support for side-by-side existence of component versions and variants.
- Isolation between components prevents interference.
- Users can install software independently from each other, without requiring mutual trust relations. Components that are common between users are shared, i.e., stored only once.
- Upgrades are atomic; there is no time window in which the system is in an inconsistent state.
- Nix supports $O(1)$-time rollbacks to previous configurations.
- Nix supports automatic garbage collection of unused components.
- The Nix component language describes not just how to build individual components, but also compositions. The language is a lazy, purely functional language. This is a good basis for a component composition language, as it allows dependencies and variability to be expressed in an elegant and flexible way.
- Nix has a transparent source/binary deployment model that marries the best parts of source deployment models such as the FreeBSD Ports Collection, and binary deployment models such as RPM. In essence, binary deployment is an automatic optimisation of source deployment.
- And more (Look at the paper).