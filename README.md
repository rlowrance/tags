Print Tags in an Org-Mode file

The Python command line program reads one or more Emacs org-mode files and prints a report on which headlines mention which tags. The report helps to manage the tags in use.

To install, clone this repo then copy the file `tags.py` to a directory that is in your path. If you use your `~/bin~ directory, you can do this by running the script `install-into-home.sh~.

To use the command, invoke the command with one or more filenames on the command line.

Here is an example: `> tags journal.org`

That command reads the file journal.org and prints to stdout a report showing each tag and for each tag, the headlines in the file that mention that tag.

# Invocation options
- `--develop` turns on additional output that I found useful as I wrote the program.
- `--help` writes help text to stdout

# Limitations

The printed report doesn't include the file name as that would be additional clutter in the output and I use the command for one file at a time.

# Contributing
The code uses these built-in Python modules:
- `argparse` to read the invocation arguments
- `collections' to create an internal data type ~TagUsage~.
- `fileinput` to read the input files specified on the command line or to read stdin, if no files are specified on the command line.

I don't follow typical guidelines for formatting source code, but you are welcome to reformat the code using your favorite style.

The license is the MIT license.

# Possible future work

- Update the script to print the file names. Then the command would be more useful for analyzing the tags across multiple files.
- Extend the kind of file analyzed to include markdown files. These have a tag syntax different from that used in org-mode files.
- Build a companion capability, possibly in the same script, to analyze tags in file names. That requires deciding on a convention for putting tags in file names. I use ` --  {tag} {tag}...` to embed tags in file names.
