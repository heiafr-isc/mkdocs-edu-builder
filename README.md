# MkDocs builder for HEIA-FR

The CI/CD of this repo builds and publish a Docker image for building
MkDocs web sites.

## How to keep this repo up-to date

Check for Python packages updates:

```
pip list --outdated
```

Update outdated Python packages

```
pip list --outdated --format=freeze | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 pip install -U
```

## Note

I used to import python-markdown-comments directly from the original author:

https://github.com/ryneeverett/python-markdown-comments

but it seems now that the package published on pypi is OK. If not, delete
the line in `requirements.txt` for `python-markdown-comments` and replace by this one:

```
-e git+https://github.com/ryneeverett/python-markdown-comments.git@aa82610f7823450f0c214473b57da8bcb0ff5651#egg=python_markdown_comments
```
