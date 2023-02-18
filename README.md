Configuring this repo:

yarn create vite
	<nome do projeto>
	React
	JavaScript
cd <nome do projeto>
npm init @eslint/config
	To check syntax, find problems, and enforce code style
	JavaScript modules (import/export)
	React
	No
	Browser
	Use a popular style guide
	Standard: https://github.com/standard/standard
	JavaScript
	Yes
	yarn
yarn add prettier
echo {}> .prettierrc.cjs
	Inside .prettierrc.cjs:
		module.exports = {
		    trailingComma: "es5",
		    tabWidth: 4,
		    semi: false,
		    singleQuote: true,
		  };
yarn add eslint-plugin-prettier
yarn add eslint-config-prettier
Inside .eslintrc.cjs:
	add "es6: true," to env
	add "'prettier'" to extends
	add "'prettier/prettier': 'error'," to rules
	add "'prettier'" to plugins
yarn add vite-plugin-checker
Inside vite.config.js:
	add "import checker from 'vite-plugin-checker'"
	add "checker({
            	eslint: {
	                lintCommand: 'eslint . --ext .js,.jsx,.ts,.tsx',
	            },
	        })," to plugins
Inside package.json:
	add ""lint": "eslint . --ext .js,.jsx,.ts,.tsx,.cjs",
	    "lint:fix": "eslint --fix . --ext .js,.jsx,.ts,.tsx,.cjs"" to scripts
ctrl+shift+p - ESLint: Restart ESLint Server
