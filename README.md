# hosta
A little utility bash script for quickly blocking sites from your browser, i.e pointing domains to localhost in your hosts file, so you can have a distraction free internet experience when you need it. 


## Usage

Clone this repo and move the folder somewhere on your PATH. 
I usually have my custom scripts in my ~/Scripts folder. 
Also make sure to make **hosta** file executable. 

```bash
git clone https://github.com/smnplk/hosta
mv hosta ~/Scripts && cd ~/Scripts/hosta && chmod +x hosta
```

### Blocking sites

Here we block facebook and nytimes. You can add one or many host arguments. 

```bash
sudo hosta block www.facebook.com www.nytimes.com
```

The above will first backup your /etc/hosts file and then add the following entries.  
127.0.0.1 www.facebook.com  
127.0.0.1 www.nytimes.com

### Restoring your hosts file

The following will undo all the changes in your /etc/hosts file, e.g your blocked sites will be unblocked. 

```bash
sudo hosta clean
```

### Killer feature

```bash
sudo hosta foff
```

The above will block facebook, youtube, reddit, hackrnews and lobsters. Those are the biggest time waisters for me, but you can edit the script and add your domains. Edit the KNOWN_DISTRACTORS list on line #9. I suggest having a keyboard shortcut for this command and the clean command. It's all you need. 

### Show current hosts file

```bash
sudo hosta show
```
