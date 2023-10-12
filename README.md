# Espanso JSON Schemas

- [About](#about)
- [Schemas](#schemas)
- [Usage](#usage)

## About

These are JSON Schema Specification compliant Schemas, which describe the requirements and options for YAML configuration and match files for the program Espanso. Based upon the documentation at <https://espanso.org>.

## Schemas

This repository includes 3 schemas:

- Espanso_Matches_File_Schema.json ← A schema for a match file, either the base file, or an application specific file.
- Espanso_Match_Schema.json ← A schema for individual matches within a match file.
- Espanso_Config_File_Schema.json ← A schema for espanso configuration files, either the base file, or application specific configurations.

## Usage

1. **Prerequisites**:

    - Before using this schema to validate your Espanso .yml files in VS Code, make sure you have the YAML extension installed in VS Code.
    - You can find the extension [here](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml).
    - Clone the schemas folder to your computer.

2. **Configuration**: To enable validation, add the following line to any Espanso match files where you want validation:

    ```yaml
    # yaml-language-server: $schema=(PATH)
    ```

    - Replace `(PATH)` with the actual path to the `Espanso_Matches_File_Schema.json` file, located in the schemas folder on your system.
    - Ensure that both `Espanso_Matches_File_Schema.json` and `Espanso_Match_Schema.json` are downloaded and kept in the same directory.
    - Note that `Espanso_Matches_File_Schema.json` depends on `Espanso_Match_Schema.json`.

3. **Validation and Completion**: After configuration, any errors will be displayed in the problems pane of VS Code. You can also take advantage of IntelliSense completions while manually editing your configuration files, like `base.yml`.

4. **Integration**: This schema is also utilized for validation in the [total_rewrite_of_snippet_cli_gem](https://github.com/ajmarkow/total_rewrite_of_snippet_cli_gem) project.

### TODO ↓

- Determine field combinations/possibilities for objects in vars array.
- Add allOf conditions array specifically for vars item subschema.
- Review Espanso docs for missed parameters.

## Resources

- Good tool to check schema/json doc for compliance with spec: <https://www.jeremydorn.com/json-editor>
- Tools for working with YAML & JSON from [JSON Formatter](https://jsonformatter.org/#:~:text=SOAP%20Formatter-,YAML,-YAML%20Validator).
- Build a react UI from a JSON Schema using [react-jsonschema-form](https://github.com/rjsf-team/react-jsonschema-form).

## License

- This software is licensed under the [GNU GENERAL PUBLIC LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) V3.
