# Readme 
IAM Right and workflows

## Stack
### Backend 
- Clojure

### Frontend
- ClojureScript
- Electron desktop
- NPM
  - [Building deps]
    - webpack
    - npm-run-all
    - cross-env
    - postcss-cli
    - postcss
    - postcss-import
    - autoprefixer

  - [Deps]
    - tailwindcss
    - Axios
    - Moment
    - React
- Clojurescript
  -
- CI
  - Github Action

- Release / Deploy: Github Action

## Usage

### Run in development locally
````dev
npm run dev
````

### Release the app


### Build the app
````shell
build.sh
````

### Deploy the app

### Libs
- Datalevin
- Quil

## Project init
Below are some instructions for the setup of the project. They may be not up to 
date, but are the initials steps.


### Fixme

```shell
mkdir cljflow
cd cljflow
mkdir {backend,domain,frontend}

# backend
cd backend
touch deps.edn
echo '{:deps {datalevin/datalevin {:mvn/version "0.8.20"}\n        com.cognitect/transit-clj {:mvn/version "1.0.329"}}}' >> deps.edn
  
# frontend
cd frontend 

# Create deps.edn
echo '{:paths
 [:src-paths :resources-paths :output-paths]

 :deps {org.clojure/clojurescript {:mvn/version "1.11.60"}
        com.bhauman/figwheel-main {:mvn/version "0.2.15"}
        reagent/reagent           {:mvn/version "1.1.0"}}

 :aliases
 {:src-paths ["src"]
  :resources-paths ["resources"]
  :output-paths ["target"]
  :dev
  {:main-opts ["--main"  "figwheel.main"
               "--build" "dev"
               "--repl"]}}}
' >> deps.edn



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

- https://curiousprogrammer.dev/blog/how-can-i-create-a-clojure-script-web-app-from-scratch-with-reagent-and-npm
- https://curiousprogrammer.dev/blog/how-can-i-use-tailwind-in-my-clojure-script-web-app
- https://www.youtube.com/watch?v=V-dBmuRsW6w&ab_channel=onthecodeagain

- Await / async avec Promesa :https://funcool.github.io/promesa/latest/promises.html
- Setup fullstack Clojure / Clojurescript app : https://www.youtube.com/watch?v=V-dBmuRsW6w&ab_channel=onthecodeagain

- Tailwind :
  - => Voir cet article https://curiousprogrammer.dev/blog/how-can-i-use-tailwind-in-my-clojure-script-web-app/
  - https://github.com/wilkerlucio/tailwind-garden

- Figma :
  - => From Figma to Tailwind : https://www.youtube.com/watch?v=6XIT2nXIbLU&ab_channel=LeeRobinson

- Storybook :
  - ShadowCLJS + Storybook https://github.com/lilactown/storybook-cljs