# Google Colab Cheatsheet

## 1. Mount your drive to access files and datasets

```python
from google.colab import drive
drive.mount('/content/drive')
```
When you run the code above, you will need to click a link and follow a process that takes about 30 seconds. When complete all of your drive files 
will be available via ‘/content/drive’ on your Colab instance, and this will allow you to structure your projects in the same way you would if you 
were using a cloud server.

## 2. Changing directory in Google colab

Use 

```python 
%cd dir_name
```

to change the current working directory for the notebook environment instead of

```python
!cd dir_name
```

If you're curious why the approach above didn't work: the issue is that each of the ```!<command>``` runs in its own subshell. So the ```!cd``` 
starts a new shell, switches directories, and then kills that shell. The ```!ls``` then starts anew in the current directory.

In general, use ```!<command>``` if the command is one that's okay to run in a separate shell. Use ```%<command>``` if the command needs to be run 
on the specific notebook.

## 3. Make sure you don’t get disconnected

```python
%%javascript
function ClickConnect(){
console.log("Working");
document.querySelector("colab-toolbar-button#connect").click()
}setInterval(ClickConnect,60000)
```

## 4. Use ```wget``` to download datasets to drive

```python
! wget -c -P '/content/drive/MyDrive/Colab Notebooks/data/' http://www.openslr.org/resources/12/train-clean-100.tar.gz
```

## 5. Use Gdown to grab publicly available Google Drive files

A shareable link to a file on Google Drive will look like this: https://drive.google.com/file/d/1-06_xAMDJ2yd75FnUOs3BK7gviO6pnoZ/view?usp=sharing

```<file_id>``` is everything between **/d/** and **/view**, in this case ```1-06_xAMDJ2yd75FnUOs3BK7gviO6pnoZ``` 

```python
## Command Line
# note, your file_id can be found in the shareable link of the file
! pip install gdown -q
! gdown — id <file_id>

## In Python
import gdown
url = https://drive.google.com/uc?id=<file_id>
output = 'my_archive.tar'
gdown.download(url, output, quiet=False)
```

## 6. Use fastprogress when the code will take some time while running ```for``` loops

```python
! pip install fastprogress
from fastprogress import master_bar, progress_bar
```

Fastprogress is a clean, well-designed progress bar library brought to you by the [fastai](https://www.fast.ai/) family.

```python
# Before
for item in my_list:
    process(item)

# After
for item in progress_bar(my_list):
    process(item)
```

## References:

1. [Configuring Google Colab Like A Pro](https://medium.com/@robertbracco1/configuring-google-colab-like-a-pro-d61c253f7573)
2. [Changing directory in Google colab](https://stackoverflow.com/questions/48298146/changing-directory-in-google-colab-breaking-out-of-the-python-interpreter)