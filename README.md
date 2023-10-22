# conventional-commits-showcase
Showcase of conventional commits and tooling for creating changelogs

## `cog` command line toolkit
This repo showcases the benefits of [conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification) in combination with [cog](https://docs.cocogitto.io/guide/#repository-initialization)

# Usage of `cog` command line tooling
- Use `cog commit` to create a conventional commit
- Use `cog check` to check if all commits are conventional commits
- Use `cog bump --auto` to bump the version
- Use `cog changelog` to generate a change log
  - TODO: Compare with git-cliff

# Characteristics of version bump with cog
- The version tag is created
- The changelog is generated and stored to a file
- The tag must not be changed otherwise auto bump does not work properly
- Cog uses [Semantic Versioning](https://semver.org/) for the version tag. 
  - API breaking features (not backward compatible) lead to a increase of major
  - API non breaking (backward compatible) new features lead to a increase of minor
  - Backward compatible bugfixes lead to a increase of patch
- You can use `cog bump --patch` to increase the patch version and so on

TEST A BREAKING CHANGE
TEST A BREAKING CHANGE AFTER 1.0.0

Breaking changes cause the `cog bump --auto` command to increase the minor version before we reached 1.0.0. Otherwise it will increase the major version. In Semver pre 1.0.0 is considered as unstable. Therefore breaking changes do not increase the major version. After reaching 1.0.0 the API is considered as stable and breaking changes cause a increase of major.

Check diff of `fix` and `feat`