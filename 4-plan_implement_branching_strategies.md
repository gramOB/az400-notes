# Configuring branches

## branch management

Branch policies
1. require viewers
2. check for linked work items
3. check for comment resolutions
4. 
Branch restrictions
5. build validations
6. status checks
7. automatic included reviewers (manual approval)
Branch protections
- prevent deletion
- prevent overwriting

# discovering branch strategy
types
- trunk: really quick branches. useful for small teams. push directly back into main directly.
- feature/task: best for ci/cd. one per story, one for feature or task. older features make it difficult to merge
  - feature flags. enabled or disabled. make feature lifecycle independent of lifecycle of code
- release: all features per release. support multiple versions in parallel, customizations. focus on specific issues. cons: difficult to maintain. multiple versions. creates double work for per version.

# pull request workflow
1. pull request - formalized process to discuss/ review the code prior to merging
2. called so because you are requesting the maitainer PULL your code into the base.
3. goals: reduce bug introduction. 4 eyes. encourage communication. speed product development.
Whats in it:
what, why, how, tests, references (ducumentation),
After making request:
Assign request > review code> good? approve and merge

# exploring code reviews
github features

# explore static code analysis
deepsource in github marketplace