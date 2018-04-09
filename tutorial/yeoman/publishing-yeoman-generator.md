---
layout: tutorialpage
title: Publishing Yeoman Generator
permalink: /tutorials/yeoman/publishing-yeoman-generator/
path: /tutorials/yeoman/
repo: https://github.com/fractus-io/yeoman-tutorial
tags: yeoman
---

As we know that Yeoman Generators, at their core, are NPM modules. So you must have a NPM account. Before publishing the generator, make sure that in package.json, you must have yeoman-generator keyword available in the keywords section, an appropriate project name, a version and with proper project description. Also make sure that the generator has a good README.md file with a generator-<generator-name> name syntax otherwise it won't appear on the Yeoman website. It should also have a GitHub repository where you will place your generator's source code. Finally publish your generator by typing in the terminal (in the working directory) as:

```
npm publish
```

After successful publishing, you will begin to see your Yeoman generator at the Yeoman's website after some time.