## Zeit Challenge

### Design Choices?

+ Choice 0
+ Choice 1

### Best Practices or Conventions?

+ .dockerignore
    + We need images to be built as fast and as lightweight as possible
    + One step we can take is to exclude irrelevant files
    + To do this without restructuring our source code, we use a .dockerignore file.
    + This file offers file exclusion functionality similar to .gitignore files.
+ Limiting layers
    + We could have a 1:1 RUN or COPY command for every file / installation necessary
    + However, this would greatly increase the number of layers in our image
    + More layers, means a slower image build and this is not ideal
    + The solution is to chain these commands as a single layer, within reason
+ Handling multi-line arguments
    + We sorted the arguments alphanumerically
    + This helps...
        + To avoid duplication of packages
        + Make updates much easier
        + Make PRs easier to read and review
