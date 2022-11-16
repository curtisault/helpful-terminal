# Writing To File

Writing to existing file.

Syntax:

```
## *BSD/macOS sed syntax ##
sed -i '' 's/foo/bar/g' input.file


## GNU/Linux sed syntax ##
sed -i 's/foo/bar/g' input.file
```

Writing to new file.


Syntax:

```
sed 's/foo/bar/g' input.file > output.file
```


View file:

```
cat input.file
```

## Expected Output

```
The is a test file created for demo purpose.
bar is good.
Foo is nice.
I love FOO.
```
