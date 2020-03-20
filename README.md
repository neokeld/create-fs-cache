# create-fs-cache
Node.js Lib forked from https://github.com/viankakrisna/loader-fs-cache

A published package of https://github.com/babel/babel-loader/blob/4b3bafa4859774458327a585d69a3c346a7652d6/src/fs-cache.js

Forked to resolve:
- https://github.com/viankakrisna/loader-fs-cache/issues/5
- https://github.com/webpack-contrib/eslint-loader/issues/316
- https://github.com/vuejs/vue-cli/issues/5285
- the same on react-scripts etc...

## Usage Example

    import createCache from 'loader-fs-cache';
    
    const cache = createCache('eslint-loader');
    
    const cacheLoader = (callback, cache, content) => {
      const cacheIdentifier = JSON.stringify({
        'create-fs-cache-example': "1.0.0",
      });
    
      cache(
        {
          directory: cache,
          identifier: cacheIdentifier,
          source: content,
        },
        (err, res) => {
          return callback(err, content);
        }
      );
    };
    
