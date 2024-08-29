### DISCLAIMER

I am not a Linux wizard. This is messy and I know it. I am still trying to learn the use of sed, cut, sort and the likes. I will try to update this page as I learn more and find better ways to do this. 


Get the updates that are available

```
apt list --upgradeable > upgrade.txt
```

Cat the .txt file, cut the line at the /, and sort. Then output to update_final.txt

```
cat upgrade.txt | cut -d "/" -f1 | sort -u > update_final.txt && echo `cat update_final.txt` > updates.txt
```

I then do the following to delete the "Listing..." entry.

```
sed -i.bak 's/Listing...//g' updates.txt
```

Then do it again as follows: Delete the whole "Gnome-shell...dashtodock" line.

```
sed -i.bak 's/{FULLGNOMESHELLDTDHERE}//g' updates.txt
```

Exit the nano text editor by using the following commands:

```
ctrl+x
y
enter
```
I then install all the updates, minus the DTD, by doing the following command:

```
sudo apt install $(cat updates.txt)
```

