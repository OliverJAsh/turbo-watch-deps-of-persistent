Persistent tasks in watch mode don't wait for first run of their dependencies to finish:

```console
$ TURBO_UI=false yarn run turbo run build --filter b
• Packages in scope: b
• Running build in 1 packages
• Remote caching disabled
a:build: cache bypass, force executing 7c09bd93554e1d1c
a:build: A
b:build: cache bypass, force executing 7f551e27d3b8aa66
b:build: B

 Tasks:    2 successful, 2 total
Cached:    0 cached, 2 total
  Time:    1.516s

$ TURBO_UI=false yarn run turbo watch build --filter b
• Packages in scope: b
• Running build in 1 packages
• Remote caching disabled
• Packages in scope: b
• Running build in 1 packages
• Remote caching disabled
a:build: cache bypass, force executing 7c09bd93554e1d1c
b:build: cache bypass, force executing 25c5580a26314aac
b:build: B
a:build: A

```
