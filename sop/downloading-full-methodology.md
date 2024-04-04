# Downloading Full Methodology

To download the entire methodology in [Markdown](https://www.markdownguide.org/), users can run the following Python code:

```python
import os
import shutil
import git
import glob

# Function to get the directory of the current script
def get_script_dir():
    return os.path.dirname(os.path.realpath(__file__))

# Clone the repository
repo_url = 'https://github.com/undp/performance-app-methodology'  # Updated repository URL
script_dir = get_script_dir()  # Get the directory of the script
repo_dir = os.path.join(script_dir, 'performance-app-methodology')  # Updated directory to clone the repo

# Check if the script_dir is writable
if not os.access(script_dir, os.W_OK):
    print(f"The directory {script_dir} is not writable. Please check your permissions.")
else:
    if not os.path.exists(repo_dir):
        git.Repo.clone_from(repo_url, repo_dir)

    # Navigate through the cloned repository and find all .md files
    md_files = glob.glob(repo_dir + '/**/*.md', recursive=True)

    # Concatenate the contents of all .md files into one
    combined_md_content = ''
    for md_file in md_files:
        with open(md_file, 'r', encoding='utf-8') as file:
            combined_md_content += file.read() + '\n\n'

    # Save the combined content into one .md file with the new filename
    combined_md_filename = os.path.join(script_dir, 'Performance App Methodology.md')
    with open(combined_md_filename, 'w', encoding='utf-8') as combined_file:
        combined_file.write(combined_md_content)

    # Delete the cloned repository directory
    if os.path.exists(repo_dir):
        shutil.rmtree(repo_dir)

    print(f'All Markdown files have been combined into {combined_md_filename}. The cloned repository has been deleted.')

```

This is useful for querying the methodology using AI, amongst other use cases.
