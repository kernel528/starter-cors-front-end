## Notes for Module 3.12.3: CORS
Notes for module setup, troubleshooting, etc

### Changes Needed to Get starter-cors-front-end to Work Properly
- https://github.com/kernel528/starter-cors-front-end
- I had to set node version to v18 `nvm use v18` as v20 and v22 had compatibility issues.
- Then I deleted the `node_modules` and `package-lock.json` to perform a fresh `npm install`.
- Had to set this environment variable to resolve error: `export NODE_OPTIONS=--openssl-legacy-provider && npm start`
    ```aiignore
    /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/react-scripts/scripts/start.js:19
    throw err;
    ^
    
    Error: error:0308010C:digital envelope routines::unsupported
    at new Hash (node:internal/crypto/hash:69:19)
    at Object.createHash (node:crypto:133:10)
    at module.exports (/home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/webpack/lib/util/createHash.js:135:53)
    at NormalModule._initBuildHash (/home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/webpack/lib/NormalModule.js:417:16)
    at /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/webpack/lib/NormalModule.js:452:10
    at /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/webpack/lib/NormalModule.js:323:13
    at /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/loader-runner/lib/LoaderRunner.js:367:11
    at /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/loader-runner/lib/LoaderRunner.js:233:18
    at context.callback (/home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/loader-runner/lib/LoaderRunner.js:111:13)
    at /home/joe/github/kernel528/Chegg-Skills/starters/starter-cors-front-end/node_modules/babel-loader/lib/index.js:59:103 {
    opensslErrorStack: [ 'error:03000086:digital envelope routines::initialization error' ],
    library: 'digital envelope routines',
    reason: 'unsupported',
    code: 'ERR_OSSL_EVP_UNSUPPORTED'
    }
    
    Node.js v18.20.4
    ```
- Then was able to successfully run `npm start`
    ```aiignore
    Compiled successfully!
    
    You can now view starter-cors-front-end in the browser.
    
      Local:            http://localhost:3002
      On Your Network:  http://192.168.1.5:3002
    
    Note that the development build is not optimized.
    To create a production build, use npm run build.
    ```