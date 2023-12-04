# vue-weather-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Deploy
```
npm run build
git add dist -f // override .gitignore dist, adds only dist to gh-pages
git commit -m "adding dist"
git subtree push --prefix dist origin gh-pages 
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
vue.config.js modul export config. including the name of the repository //   publicPath: process.env.NODE_ENV === 'production' ? '/vue-weather-app/' : '/'  
