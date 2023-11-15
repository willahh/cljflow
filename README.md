# Readme 

## TODO
Gestion users, groupes, droit, workflow

### Libs
- [ ] Datalevin
- [ ] Quil

## Project init
Below are some instructions for the setup of the project. They may be not up to 
date, but are the initials steps.

Stack : 
 - Clojure
 - ClojureScript
 - Shadow CLJS


```shell
mkdir cljflow
cd cljflow
mkdir {backend,domain,frontend}

# backend
cd backend
touch deps.edn
echo '{:deps {datalevin/datalevin {:mvn/version "0.8.20"}\n        com.cognitect/transit-clj {:mvn/version "1.0.329"}}}' >> deps.edn
  
# frontend
# Setup of the frontend with the official doc with webpack 
#  - https://clojurescript.org/guides/webpack
#  - https://dev.to/romanliutikov/integrating-clojurescript-with-javascript-tooling-3799
cd frontend
mkdir out
mkdir -p src/cljflow/frontend
echo '{:deps {org.clojure/clojurescript {:mvn/version "1.11.60"}}}' >> deps.edn
echo "{}" > package.json
npm install webpack webpack-cli --save-dev
npm install react react-dom --save

## Create entry cljs namespace
echo '(ns cljflow.frontend.core
  (:require [react]))

(.log js/console react/Component)' >> src/cljflow/frontend/core.cljs

## Create build.edn
echo '{:main cljflow.frontend.core
 :output-to "out/index.js"
 :output-dir "out"
 :target :bundle
 :bundle-cmd {:none ["npx" "webpack" "--mode=development"]
              :default ["npx" "webpack"]}}' >> build.edn
 
## Create webpack config
echo 'module.exports = {
  entry: "./out/index.js",
  output: {
    path: __dirname,
    filename: "bundle.js"
  }
}' >> webpack.config.js

## Create root html file
echo '<div id="root"></div><script src="bundle.js"></script>' > index.html

## Testing
clj -M -m cljs.main -co build.edn --compile --repl
```


## Build
````sh
clj -m cljs.main -co build.edn -O advanced --compile --serve 
````


## Setup 
- 

## Resources
- https://clojurescript.org/guides/webpack
- https://cljdoc.org/d/datalevin/datalevin/0.8.20/doc/installation
- Full Stack Clojure App - clojure/script + deps.edn + shadow-cljs + Helix + Tailwind
  https://www.youtube.com/watch?v=V-dBmuRsW6w&ab_channel=onthecodeagain