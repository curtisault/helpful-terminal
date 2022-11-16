# Print Only Changed Lines

Use the -n option along with the /p print flag to display only the replaced lines. Here the -n option suppresses the duplicate rows generated by the /p flag and prints the replaced lines only one time.

```
$sed -n 's/unix/linux/p' input.file
```

View file:

```
cat input.file
```

## Expected Output

```
linux is great os. unix is opensource. unix is free os.
linux linux which one you choose.
linux is easy to learn.unix is a multiuser os.Learn unix .unix is a powerful.
```