# GitHub Content Downloader

A powerful command-line tool to download files and folders from GitHub repositories. Download any file or entire directory from GitHub repositories without cloning - perfect for selectively downloading specific content.

## Features

- Download single files from GitHub repositories
- Download entire folders recursively
- Download complete repositories
- Simple command-line interface (`ghcd`)
- Support for both file URLs (blob) and folder URLs (tree)
- Customizable download location
- No authentication required for public repositories

## Installation

### Option 1: Install from PyPI

```bash
pip install github-content-downloader
```

### Option 2: Install from source

```bash
# Clone the repository
git clone https://github.com/soykot2910/github-content-downloader.git

# Navigate to the project directory
cd github-content-downloader

# Install the package
pip install .
```

## Usage

### Command Line Interface

1. Download a complete repository:
```bash
ghcd https://github.com/username/repository
```
Example:
```bash
ghcd https://github.com/tensorflow/tensorflow
```

2. Download a specific folder:
```bash
ghcd https://github.com/username/repository/tree/branch/folder
```
Example:
```bash
ghcd https://github.com/tensorflow/tensorflow/tree/master/tensorflow/python
```

3. Download a single file:
```bash
ghcd https://github.com/username/repository/blob/branch/path/to/file
```
Example:
```bash
ghcd https://github.com/tensorflow/tensorflow/blob/master/README.md
```

4. Specify custom output directory:
```bash
ghcd -o ./my-downloads <github-url>
```

5. Interactive mode (if no URL provided):
```bash
ghcd
```

### Command Line Options

```bash
ghcd --help
```

Available options:
- `-o, --output`: Specify output directory (default: ./downloaded_files)
- `-h, --help`: Show help message

### Python Package Usage

You can also use it as a Python package in your code:

```python
from github_downloader import download_from_github

# Download complete repository
download_from_github("https://github.com/username/repository")

# Download specific folder
download_from_github(
    "https://github.com/username/repository/tree/master/docs",
    dest_folder="./my-downloads"
)

# Download single file
download_from_github(
    "https://github.com/username/repository/blob/master/README.md"
)
```

## URL Format Examples

### 1. Complete Repository
```
https://github.com/username/repository
```
Downloads the entire repository from the default branch (usually 'master' or 'main').

### 2. Specific Folder
```
https://github.com/username/repository/tree/branch/path/to/folder
```
Downloads only the specified folder and its contents.

### 3. Single File
```
https://github.com/username/repository/blob/branch/path/to/file
```
Downloads only the specified file.

## Common Issues and Solutions

1. **Permission Error**: If you get a permission error while downloading, make sure you have write permissions in the output directory.

2. **Invalid URL Format**: Make sure your GitHub URL follows one of these patterns:
   - Repository: `https://github.com/username/repo`
   - Folder: `https://github.com/username/repo/tree/branch/path`
   - File: `https://github.com/username/repo/blob/branch/path`

3. **Download Failed**: If downloads fail, check:
   - Your internet connection
   - The repository is public and accessible
   - The URL is correct and the resource exists

## Requirements

- Python 3.6 or higher
- `requests` library (automatically installed with the package)

## Development

Want to contribute? Great! Here's how:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Install development dependencies:
```bash
pip install -e .
```
4. Make your changes
5. Commit your changes (`git commit -m 'Add some amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

- Md.Soykot
- Email: md.soykot2910@gmail.com
- GitHub: [@soykot2910](https://github.com/soykot2910)

## Support

If you encounter any issues or have questions, please:
1. Check the [Common Issues](#common-issues-and-solutions) section
2. Open an issue on GitHub
3. Contact the author via email

## Acknowledgments

- Thanks to GitHub for providing their API
- Inspired by the need to download specific parts of repositories without cloning