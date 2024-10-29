# Save Script

A simple shell script to save piped input to markdown files with automatic date prefixing and incremental naming. This script was inspired by and adapted from a [community discussion](https://github.com/danielmiessler/fabric/issues/831#issuecomment-2304875874) in the Fabric project.

## Features

- Automatically prefixes files with the current date (YYYY-MM-DD)
- Creates incremental file numbers if a file with the same name exists
- Supports custom file names
- Reads from environment file for default save location
- Allows override of save location via command line flag

## Installation

1. Save the script to a location in your PATH (e.g., `~/.local/bin/save`)
2. Make it executable:
   ```bash
   chmod +x ~/.local/bin/save
   ```

## Configuration

The script looks for a configuration file at `~/.config/fabric/.env`. You can specify your default save location by setting:
    ```bash
    FABRIC_OUTPUT_PATH="/path/to/your/default/directory"
    ```

## Usage

Basic usage (saves as current-date-note.md):
    ```bash
    echo "Some content" | save
    ```

Save with custom filename (saves as current-date-customname.md):
    ```bash
    echo "Some content" | save "customname"
    ```

Specify alternative directory:
     ```bash
     echo "Some content" | save -d "/alternative/path"
    ```

## Output Format

Files are saved with the following naming convention:
- `YYYY-MM-DD-filename.md` (base format)
- `YYYY-MM-DD-filename-1.md` (when file exists, incremental number is added)

## Credits

Original concept and base implementation discussed in the [Fabric project issue #831](https://github.com/danielmiessler/fabric/issues/831#issuecomment-2304875874) by community members @caunus and @RFingAdam.

## License

This script is provided as-is under the MIT License.