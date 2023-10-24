# Readme 

## Project init
Below are some instructions for the setup of the project. They may be not up to 
date, but are the initials steps.

```shell
mkdir cljflow
cd cljflow
mkdir {backend,domain,frontend}

# backend
cd backend
touch deps.edn
echo '{:deps {datalevin/datalevin {:mvn/version "0.8.20"}\n        com.cognitect/transit-clj {:mvn/version "1.0.329"}}}' >> deps.edn
  
# frontend
# Setup of the frontend with the official doc with webpack https://clojurescript.org/guides/webpack
cd frontend
echo '{:deps {org.clojure/clojurescript {:mvn/version "1.11.60"}}}' >> deps.edn
echo "{}" > package.json
npm install --save-dev webpack webpack-cli
npm install --save react react-dom


```
- frontend
  - https://clojurescript.org/guides/webpack


## Setup 
- 

## Resources
- https://clojurescript.org/guides/webpack
- https://cljdoc.org/d/datalevin/datalevin/0.8.20/doc/installation