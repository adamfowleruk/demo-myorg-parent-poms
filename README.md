# demo-myorg-parent-poms

Parent POM files for various Spring Boot archetypes.

In applications we're used to specifying a Spring Boot parent version and POM.
In real world applications, you may want to centralise the choice of versions
of spring boot and various dependencies for a subset of known, limited,
application archetypes. A database backed REST service would have a different
set of dependencies, for example, to a web UI application.

Doing this also allows an org to build a standard container build process
for spring boot applications (much like buildpacks.io does), and externalise
the choice of base version (and thus base docker image) under the app. This allows
for rapid deployment and automation of CVE fixes to all apps in production using
the same archetype. Rather than ask all my developers to manually change all their
POMs, I can instead change one parent POM, run a smoke test on this, and then
push the CVE fix to all running apps within minutes.

This repository provides an example of how to do this with a limited set of
Spring Boot archetypes. See the (demo-paving)[https://github.com/adamfowleruk/demo-paving]
repository for how this is automated using the (poor mans) 'build pack'
dockerfiles present in my (demo-base-images)[https://github.com/adamfowleruk/demo-base-images]
repository.

## License

All code is Apache-2.0 unless otherwise stated.

## Further examples

Here are some useful links for further reading on this approach:-

- https://github.com/qbicsoftware/parent-poms
