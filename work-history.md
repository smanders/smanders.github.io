# Work History

<link rel="stylesheet" href="style.css">

## Sorenson Media (1997-2002)

### Extensible video codec framework
As a software engineer at [Sorenson](https://en.wikipedia.org/wiki/Sorenson_Media), I designed and implemented a video codec (compression/decompression) framework to run under several multimedia architectures (QuickTime, Video For Windows, DirectShow, MPEG-4). This layer allowed us to have a common base for all codecs while still supporting the specific requirements of each architecture.

### Compression algorithm guru
I was responsible for the architecture, implementation, and optimization of our core encoding algorithms, which differentiated our compression performance from competitors. My expertise included extensive research in the area of motion estimation. I led an engineering team in implementing the Sorenson Video 3 codec, which was based on an early specification of H.26L. Codec implementations I was a part of include: H.263, H.261, MPEG-4 Visual (Simple and Advanced Simple Profiles), H.264 (aka JVT, MPEG-4 Part 10 AVC)

### Optimization expertise
I optimized our codecs for specific processor architecture instruction sets: MMX, SSE (Streaming SIMD Extensions), SSE2, and Altivec. We once took a work trip to an Intel facility to have them help us evaluate whether their Integrated Performance Primitives (IPP) library would provide better performance than our custom implementations. When my DCT (discrete cosine transformation) implementation proved to be faster than the IPP library, they wanted to examine and understand my implementation.

## Space Dynamics Laboratory (2003-2025)
When I started at Space Dynamics Laboratory in 2003 the C4ISR division of less than 20 software engineers was supporting three products in three separate svn code repositories running on Solaris and Windows, with GUIs using [Motif](https://en.wikipedia.org/wiki/Motif_(software)) and utilizing Cygwin for it to work on Windows. My first tasks involved porting fixes from one repository to the others where common, duplicated code was in abundance.

I transformed software development by pioneering ten key technologies. Each initiative was proposed, implemented, and maintained by me, making me the resident expert in every technology introduced. I was self-taught in every one of these technologies and then taught and mentored others.

### Library architect
First order of business was a shared code repository with an extensive set of libraries that could be used (and reused) by our products. There were nearly a hundred static libraries (many libraries were a single C++ class), with circular dependencies, duplicated code, and poorly designed public interfaces. I organized the code base into a set of libraries with dependencies between them that brought sanity and order to the chaos. This enabled our group to reach new levels of efficiency and opened the door to develop and support many more products built on top of these shared libraries. I was the primary maintainer and grew this suite of libraries over two decades. When someone proposed a new library they would consult with me. I was "the library architect guy".

### Cross-platform user interfaces
The second major undertaking was moving our Motif user interfaces to a more cross-platform technology, leveraging wxWidgets. I wrote the first wxWidgets applications, ported existing applications from Motif to wx, and learned the ins-and-outs of building wx, writing code that used it, and teaching others best practices. I was "the cross-platform wxWidgets guy".

### CMake adoption
The third major effort was adopting CMake when Solaris support returned. Our Makefiles were in disrepair and we only maintained Visual Studio files. I discovered, proposed, and implemented the switch to CMake, a natural progression from my library work. I implemented Modern CMake best practices and became "the CMake guy".

### CPack installers
The fourth strategic evolution came as I self-learned and took deep dives into what the CMake project offered. We had been maintaining different ways of packaging our software for the platforms we supported. I discovered CPack and extended it to support creating Solaris pkg installers, evolving from NSIS to WIX generators for Windows. I added Linux RPM support and wrote reusable cmake functions for pre/post install scripts. I was "the installer guy".

### Image Compression
The fifth pioneering initiative was expanding our image compression capabilities. We had previously handled 8-bit lossy JPEG and had a contorted way of dealing with 12-bit JPEG, but I modified the libjpeg repository in a very novel way (see [jpegxp](https://github.com/externpro/jpegxp)) and wrote a wrapper JpegCodec class so we also supported JPEG 12-bit lossy and JPEG lossless decoding. I integrated a couple open source JPEG 2000 libraries and a JPEG XR library and showcased support for JPIP. An abstract base class named ImageCodec enabled developers to write code that was agnostic to the compression algorithm. I wrote an application that enabled us to visually and systematically compare compression algorithms with PSNR graphs and timing metrics. I was "the image compression guy".

### Git adoption and release process
The sixth paradigm shift was the adoption of Git. We had been using svn for version control. I proposed and implemented the switch to Git, keeping our extensive svn commit history and breaking up the massive code base into logical git repositories, leveraging the power of git submodules. I trained, supported, and mentored other developers on how to use Git effectively. I was often called upon to help developers with Git-related issues. I implemented the latest Git-related best practices (GitFlow, etc.). I established the organization's release process and versioning strategy, implementing automated release workflows that ensured consistent, traceable software deliveries across all projects. I was "the Git guy".

### GitHub instigator
The seventh strategic move was the adoption of GitHub. I advocated for and implemented GitHub Enterprise, replacing our internal Git server. I managed organizations, repositories, and license optimization while keeping myself up-to-date with the latest GitHub features and best practices. I helped with the design of our process-specific CI/CD pipelines using GitHub Actions, and was always leading the charge to leverage new GitHub features and capabilities (milestones, issues, projects, actions, and later the GitHub Container Registry). I was "the GitHub guy".

### Legacy externpro
The eighth foundational change was the creation of what I now call "legacy externpro". As our team, code base, and requirements grew, we needed a way to manage dependencies and share pre-built libraries and binaries across projects. Early attempts by other developers failed due to little documentation, inconsistent builds, and missing platform support. Updating dependencies to newer releases or compilers became a nightmare because the process was manual and undocumented. Drawing on my CMake expertise, I discovered CMake's ExternalProject module and created externpro (named for this CMake feature). I convinced management to open-source it at [smanders/externpro](https://github.com/smanders/externpro). The framework uses a four-step process (make patch, download, patch, build) to create a big bundle of build artifacts (one large tar.xz file per platform and compiler), eliminating manual management and boosting productivity. I organized the cmake functions and macros to be reusable, which enabled the creation of internpro (internal projects) and webpro (web projects) frameworks. I maintained projects to keep them current with newer releases, security patches, static code analyzer fixes, and compiler releases. I was "the pre-built external libraries guy".

### Docker solution
The ninth transformational evolution was the adoption of Docker. I introduced Docker to solve inconsistent development environments, replacing unreliable Linux systems with standardized containers. This enabled Windows developers to build Linux locally via WSL2. I created a configurable and extensible system of Dockerfiles and Docker Compose files to support various development groups with different needs, from microservices to plugins. I was "the Docker guy".

## Priority 6 (2025-present)

### New externpro framework
The tenth and final groundbreaking initiative began at Space Dynamics Lab but was cut short when I left. I've continued this work at Priority 6, a startup where I've been implementing a complete overhaul of the externpro framework to make it more modern, efficient, and easier to use. This framework leverages nearly the full spectrum of my expertise: CMake, Git, GitHub, legacy externpro, and Docker. Within a short amount of time I taught myself and implemented an extensive set of GitHub Actions that automate the framework's build and testing, while also making these CI pipelines available to any project that includes externpro as a git submodule. I've also become proficient at leveraging AI technologies, particularly Windsurf Cascade, to accelerate development and testing. The result is a world-class CMake build platform and dependency provider with reusable CI pipelines. The expanded feature set supports multiple architectures, operating systems, and compiler releases while addressing software supply chain security through SBOMs and attestation. Extensive automated cross-platform testing quickly catches regressions and ensures reliability across multiple architectures and platforms. The externpro framework is now production-ready and requires fewer changes to an upstream release. I am "the externpro guy".

## Future

### Technical leadership & continuous learning
What sets me apart is not just my depth of expertise across multiple domains, but my proven ability to rapidly master and implement emerging technologies. From pioneering video codec optimizations at Sorenson to transforming SDL's entire development ecosystem, I've consistently identified critical business challenges and taught myself the solutions—from wxWidgets and CMake to Docker and modern CI/CD pipelines. Each initiative began with me diving deep into unfamiliar technologies, becoming the resident expert, and then mentoring entire teams. This pattern of self-directed learning, combined with nearly three decades of architecting scalable solutions, demonstrates my capacity to quickly adapt to any technical challenge and deliver production-ready systems that serve both immediate needs and long-term strategic goals.
