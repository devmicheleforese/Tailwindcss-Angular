# How to Setup Tailwind in an Angular Application

1. Install the Angular CLI

    ```sh
    npm install -g @angular/cli
    ```

2. Create an Angular Appplication

    ```sh
    ng new <application_name>
    ```

    where <applicazion_name> is the name of the project/app.

3. Install npm Packages

    ```sh
    npm i -D tailwindcss postcss postcss-scss postcss-import postcss-loader autoprefixer @angular-builders/custom-webpack
    ```

4. Initialize Tailwind

    ```sh
    npx tailwind init
    ```

6. Create a "webpack.config.js" file

   ```sh
   touch webpack.config.js
   ```

7. Insert this in the file:

    ```js
    module.exports = {
        module : {
            rules: [
				{
					test   : /\.scss$/,
					loader : 'postcss-loader',
					options: {
						postcssOptions: {
							ident: 'postcss',
							syntax: 'postcss-scss',
							plugins: [
							require('postcss-import'),
							require('tailwindcss'),
							require('autoprefixer'),
							],
						}
					}
				}
            ]
        }
    };
    ```

5. Change the Builder option

   ```json
	"architect": {
		"build": {
			"builder": "@angular-builders/custom-webpack:browser",
			"options": {
				"customWebpackConfig": {
					"path": "./webpack.config.js"
				},
			}
		},
		"serve": {
			"builder": "@angular-builders/custom-webpack:dev-serve",
			"options": {
				"customWebpackConfig": {
					"path": "./webpack.config.js"
				},
			}
		},
		"test": {
			"builder": "@angular-builders/custom-webpack:karma",
			"options": {
				"customWebpackConfig": {
					"path": "./webpack.config.js"
				},
			}
		}
	}
	```

8. Insert the tailwind imports

    ```scss
    @import 'tailwindcss/base';
	@import 'tailwindcss/components';
	@import 'tailwindcss/utilities';
    ```
