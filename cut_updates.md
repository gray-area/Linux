Get the updates that are available

```
apt list --upgradeable > upgrade.txt
```

Cat the .txt file, cut the line at the /, and sort. Then output to update_final.txt

```
cat upgrade.txt| cut -d "/" -f1 | sort -u > update_final.txt
```

Check my work

```
cat update_final.txt
```

Copy the contents of the file an place it in Notepad++

Highlight all and select:

```
Edit > Line Operations > Join Lines
```

Copy and paste this whole line in the terminal.

```
sudo apt install <LIST GOES HERE>
```
