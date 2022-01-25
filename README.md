# monorepo-poc
used nextjs and lerna
steps:
     git init building-monorepos-using-lerna && cd building-monorepos-using-lerna
     lerna init
     cd packages && yarn create next-app front-end
     lerna create components
     cd packages/components && yarn add microbundle -D
     add one script inside our components package’s package.json file: "scripts": {
                                                                                     "dev": "microbundle watch --jsx React.createElement"
                                                                                  }
     add a source to the package.json file:"source": "lib/index.js"
     connect our front-end package with our components package.add components as dependancy to front-end
     npx lerna clean -y
     npx lerna bootstrap --hoist
     npx lerna run dev --parallel
