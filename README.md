# sanitize-filenames

macOS workflow to sanitize filenames.

A workflow that you can use to handle weird characters in filenames.

## Usage

- Download the zip file
- Extract the app
- Run the app
- It'll ask you for a folder name
- Done

## What it does

It creates a Workflow applicatoin doing the following:

- Asks for Finder items (you should allow only folders)
- Sets this result as a variable
- It runs a shell script to do the renaming

The script is:

```bash
for f in "$1"/*; do
  dir="$(dirname "$f")"
  file="$(basename "$f")"
  mv -- "$f" "${dir}/${file//[^0-9A-Za-z.]}"
done
```

## License

Do whatever you want with this.
