#### 4. Running parallel jobs
download and extract the package to your working repository.

Using following template create 3 parallel jobs for ruby 2.2, ruby 2.3 and ruby 2.4
Tips:

images to use:
circleci/ruby:<ruby-version>-node
circleci/postgres:9.4.12-alpine
Commands to use
````
bundle install --path vendor/bundle
bundle exec rake db:create db:schema:load
rake
````

template:

````
version: 2.0
jobs:
  "<workflow1>":
    docker:
      <image>
    working_directory: ~/testing-workflows
    steps:
      - <command>
workflows:
  version: 2
  build:
    jobs:
      - workflow1
````          
some workflows may fail ;)

