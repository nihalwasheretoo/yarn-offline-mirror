# yarn-offline-mirror

Test repo supporting yarn offline mirror

1. The folder `npm-packages-offline-cache` consists of the package tarballs that we don't need to fetch again and again from the network.

2. `yarn.rc` consists of our offline-mirror configuration.

3. `yarn-offline-mirror "./npm-packages-offline-cache"` in `yarn.rc` specifies the path for yarn to look up in case of fetching packages offline.

4. `yarn-offline-mirror-pruning true` in `yarn.rc` specifies to remove any unlinked dependencies.

## Steps to install packages offline

1. Make sure to clear yarn's global cache.

```
$ yarn cache clean
```

2. Remove `node_modules` if you did a `yarn install` to install packages over network.

3. Install through offline mirror.

```
$ yarn install --offline
```

More info here : https://yarnpkg.com/blog/2016/11/24/offline-mirror/
