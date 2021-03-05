# publish-python-package
### Publish a python package in as little commands as possible

#### 1. Change to project folder
`cd <project/path/here/package_name>`

#### 2. Package files
`for /D %a in ("<package_name>.egg-info" "build" "dist") do rd /s /q %~a`\
(`python -m pip install --upgrade build`) - if not already installed\
`python -m build`

#### 3. Upload files
(`python -m pip install --user --upgrade twine`) - if not already installed\
`python -m twine upload --repository-url https://upload.pypi.org/legacy/ dist/*`

#### All one ctrl V
`cd <project/path/here/package_name>`\
`for /D %a in ("<package_name>.egg-info" "build" "dist") do rd /s /q %~a`\
`python -m build`\
`python -m twine upload --repository-url https://upload.pypi.org/legacy/ dist/*`
