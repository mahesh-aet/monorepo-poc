# monorepo-poc
# used next-js and lerna
# steps:
     1. git init building-monorepos-using-lerna && cd building-monorepos-using-lerna
     2. lerna init
     3. cd packages && yarn create next-app front-end
     4. lerna create components
     5. cd packages/components && yarn add microbundle -D
     6. add one script inside our components package’s package.json file: "scripts": {
                                                                                     "dev": "microbundle watch --jsx React.createElement"
                                                                                  }
     7. add a source to the package.json file:"source": "lib/index.js"
     8. connect our front-end package with our components package.add components as dependancy to front-end
     9. npx lerna clean -y
     10. npx lerna bootstrap --hoist
     11. npx lerna run dev --parallel
