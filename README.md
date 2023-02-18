Configuring this repo:

`yarn create vite`\
	&emsp;nome do projeto\
	&emsp;React\
	&emsp;JavaScript\
`cd <nome do projeto>`\
`npm init @eslint/config`\
	&emsp;To check syntax, find problems, and enforce code style\
	&emsp;JavaScript modules (import/export)\
	&emsp;React\
	&emsp;No\
	&emsp;Browser\
	&emsp;Use a popular style guide\
	&emsp;Standard: https://github.com/standard/standard \
	&emsp;JavaScript\
	&emsp;Yes\
	&emsp;yarn\
`yarn add prettier`\
`echo {}> .prettierrc.cjs`\
	&emsp;Inside .prettierrc.cjs:\
		&emsp;&emsp;```
		module.exports = {\
		    trailingComma: "es5",\
		    tabWidth: 4,\
		    semi: false,\
		    singleQuote: true,\
		  };
		  ```\
`yarn add eslint-plugin-prettier`\
`yarn add eslint-config-prettier`\
Inside .eslintrc.cjs:\
	&emsp;add `es6: true,` to `env`\
	&emsp;add `'prettier'` to `extends`\
	&emsp;add `'prettier/prettier': 'error',` to `rules`\
	&emsp;add `'prettier'` to `plugins`\
`yarn add vite-plugin-checker`\
Inside vite.config.js:\
	&emsp;add `import checker from 'vite-plugin-checker'`\
	&emsp;add 
	```
	checker({\
            	eslint: {\
	                lintCommand: 'eslint . --ext .js,.jsx,.ts,.tsx',\
	            },\
	        &emsp;}),
		```
		to `plugins`\
Inside package.json:\
	&emsp;add 
	```
	"lint": "eslint . --ext .js,.jsx,.ts,.tsx,.cjs",\
	    "lint:fix": "eslint --fix . --ext .js,.jsx,.ts,.tsx,.cjs"
	    ```
	    to `scripts`\
ctrl+shift+p - ESLint: Restart ESLint Server\
