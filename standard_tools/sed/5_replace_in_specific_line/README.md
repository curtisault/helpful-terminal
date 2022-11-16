# Replace in Specific Line

You can restrict the sed command to replace the string on a specific line number.

```
$sed '3 s/unix/linux/' input.file
```

View file:

```
cat input.file
```

## Expected Output

```
unix is great os. unix is opensource. unix is free os.
learn operating system.
linux linux which one you choose.
unix is easy to learn.unix is a multiuser os.Learn unix .unix is a powerful.
```
