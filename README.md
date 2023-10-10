# Espanso JSON Schema

## Table of Contents

- [About](#about)
- [Usage](#usage)

## About

A JSON Schema Specification compliant Schema which describes the requirements and options for YAML objects/config files for the program Espanso. Based upon the documentation at <https://espanso.org>.

TODO: Clarify what schema this is validated against, should be 2020-12 draft.

### Prerequisites

A validator or client which can utilize JSON Schema to validate the schema of your YAML code

## Usage

1. **Prerequisites**: Before using this schema to validate your Espanso .yml files in VS Code, make sure you have the YAML extension installed in VS Code. You can find the extension [here](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml).

2. **Configuration**: To enable validation, add the following line to any Espanso match files where you want validation:

    ```yaml
    # yaml-language-server: $schema=(PATH)
    ```

    - Replace `(PATH)` with the actual path to the `Espanso_Matches_File_Schema.json` file, located in the schemas folder on your system.
    - Ensure that both `Espanso_Matches_File_Schema.json` and `Espanso_Match_Schema.json` are downloaded and kept in the same directory.
    - Note that `Espanso_Matches_File_Schema.json` depends on `Espanso_Match_Schema.json`.

3. **Validation and Completion**: After configuration, any errors will be displayed in the problems pane of VS Code. You can also take advantage of IntelliSense completions while manually editing your configuration.

4. **Integration**: This schema is also utilized for validation in the [total_rewrite_of_snippet_cli_gem](https://github.com/ajmarkow/total_rewrite_of_snippet_cli_gem) project.

### TODO ↓

- Determine field combinations/possibilities for objects in vars array.
- Add allOf conditions array specifically for vars item subschema.
- Determine how to add/refactor recursive params, aka params that are used in another variable definition.

### Resources

- Good tool to check schema/json doc for compliance with spec: <https://www.jeremydorn.com/json-editor>
