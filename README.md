# tipCommands

### Find a text and reemplace, recursive:
  ```
   find . -type f -exec sed -i 's/TEXT_TO_FIND/\\TEXT\\TO\\REEMPLACE/g' {} \;
  ```
