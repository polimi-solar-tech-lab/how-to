# Cheat Sheet

Install any package with pip
- `!pip install myPackage`

Import your own custom package
- Connect google drive to your colab session
  ```python
  import sys
  sys.path.append('/content/drive/MyDrive/myPackage/')
  import myPackage
  ```
