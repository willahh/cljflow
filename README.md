# Readme 

## TODO
Gestion users, groupes, droit, workflow

### Libs
- [ ] Datalevin
- [ ] Quil

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
mkdir out
mkdir -p src/cljflow/frontend
echo '{:deps {org.clojure/clojurescript {:mvn/version "1.11.60"}}}' >> deps.edn
echo "{}" > package.json
npm install --save-dev webpack webpack-cli
npm install --save react react-dom

## Create entry cljs namespace
echo '(ns cljflow.frontend.core
  (:require [react]))

(.log js/console react/Component)' >> src/cljflow/frontend/core.cljs

## Create build.edn
echo '{:main cljflow.frontend.core
 :output-to "out/index.js"
 :output-dir "out"
 :target :bundle
 :bundle-cmd {:none ["npx" "webpack" "./out/index.js" "-o" "out" "--mode=development"]
              :default ["npx" "webpack" "./out/index.js" "-o" "out"]}
 :closure-defines {cljs.core/*global* "window"}} ;; needed for advanced' >> build.edn


```


## Setup 
- 

## Resources
- https://clojurescript.org/guides/webpack
- https://cljdoc.org/d/datalevin/datalevin/0.8.20/doc/installation