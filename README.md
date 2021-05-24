# Docusaurus Plugin Dotenv 📦

A Docusaurus2 plugin that provides out-of-the-box support for Dotenv.

## Install

Install the plugin with npm or yarn:

```sh
npm install docusaurus-plugin-dotenv
```

or

```sh
yarn add docusaurus-plugin-dotenv
```


## Description

The `docusaurus-plugin-dotenv` plugin uses [`dotenv-webpack`](https://github.com/mrsteele/dotenv-webpack) to enable Dotenv support in Docusaurus2+ projects. This allows you to access your environment variables via `process.env.VARIABLE_NAME` in your code.

## Usage

The plugin can be used "out of the box" using the standard configuration. In your `docusaurus.config.js` file, add the following to your `plugins` block.

```javascript
module.exports = {
  // ...
  plugins: [
    // ...
    'docusaurus-plugin-dotenv'
  ]
};
```

## Options

Use the following properties to configure the `dotenv-webpack`.

- **path** (`'./.env'`) - The path to your environment variables.
- **safe** (`false`) - If true, load '.env.example' to verify the '.env' variables are all set. Can also be a string to a different file.
- **systemvars** (`false`) - Set to true if you would rather load all system variables as well (useful for CI purposes).
- **silent** (`false`) - If true, all warnings will be suppressed.
- **expand** (`false`) - Allows your variables to be "expanded" for reusability within your `.env` file.
- **defaults** (`false`) - Adds support for `dotenv-defaults`. If set to `true`, uses `./.env.defaults`. If a string, uses that location for a defaults file.
- **ignoreStub** (`false`) - Override the automatic check whether to stub

```javascript
docusaurus.config.js

module.exports = {
    // ...
    plugins: [
        [
            'docusaurus-plugin-dotenv',
            {
                path: "./.env", // The path to your environment variables.
                safe: false, // If false ignore safe-mode, if true load './.env.example', if a string load that file as the sample
                systemvars: false, // Set to true if you would rather load all system variables as well (useful for CI purposes)
                silent: false, //  If true, all warnings will be suppressed
                expand: false, // Allows your variables to be "expanded" for reusability within your .env file
                defaults: false, //  Adds support for dotenv-defaults. If set to true, uses ./.env.defaults
                ignoreStub: true
            }
        ]
    ],
    // ...
}
```
