# Foundations

In order to fuel a strong capability of rapid application development and deployment, I've been thinking about what I would build to unlock my developers.

## Goals
- don't force the development language
- don't force the app communication style
  - async via RabbitMQ / Kafka
  - sync via gRPC / Thrift

## Requirements
- leverage a protocol like Protocol Buffers or Avro
  - The goal here is to define a language independentnt schema of the messages
    - https://developers.google.com/protocol-buffers/
    - https://avro.apache.org/docs/current/
- leverage type systems to reduce bugs and increase self documentationness

## Thoughts on language choices

My current list of languages I like are:

- F#: Functional, massive .Net support, cross platform, scriptable and compiled, statically typed, runtime meta data
- C#: Same as F# with less functionalness
- Rust: awesome type system, native, fast - but strings are a bit PITA

### Languages I wouldn't use
Not that they are bad, just not ones I'm investing in for my own use
- Python: Love this language, but no types
- Ruby: This language is insanity to me
- Java: Would rather use .Net
- Clojure: Lack of typing, otherwise awesome
- Node/JavaScript: Callback hell, no typing

### On the fence about
- TypeScript
- JavaScript with Flow - i think I'm waiting for async/await to come to fruition
- Reason - see how long it lasts

## Thoughts on Operating System choice
The more I think about this, the more I feel like it has to be a linux environment so that I can automate the infrastructure. Window's just isn't there yet.
- CoreOS: https://coreos.com/why/ - auto updating minimal OS - for docker usage
- RancherOS: http://rancher.com/rancher-os/ - minimal OS for docker usage
- Debian: the more minimal than ubuntu but still has APT-GET
- Ubuntu: easier dev setup based on Debian and has APT-GET
- I want to look at NixOS: https://nixos.org/ - could have an even better package manager

## Thoughts on Cloud Providers
- AWS: The default
- DigitalOcean: Would like to look at and compare to AWS for simpler requirements

## CI tools
- Gitlab CI
- AppVeyor
- CodeShip 

### Make sure you have a private registry
- DockerHub for docker images
- Then set up the language specific registry for your choosen language
- You may need multiple to support your teams workflow (a npm one for the UIUX team and a NuGet one for the .Net team)

## CD Tools

## Infrastructure tooling
- Terraform
- Consul
- Packer

## Workload Scheduling
- Mesos / Mesosphere / DC/OS
- Kubernetes

## "Micro" Services

I like this series on moving to services

http://blog.gemnasium.com/post/145001327420/from-monolithic-to-micro-services-part-1-4
http://blog.gemnasium.com/post/145658885659/from-monolithic-to-micro-services-part-2
http://blog.gemnasium.com/post/146701089939/from-monolithic-to-micro-services-part-3
http://blog.gemnasium.com/post/147286451971/from-monolithic-to-micro-services-part-4