# Python-GUI-Mp4-downloader

Source Video - [Youtube](https://www.youtube.com/watch?v=6stlCkUDG_s)

## Python Code

```python
import tkinter as tk
from pytube import YouTube

def convert():
    link = userInput.get()
    youtubeObject = YouTube(link)
    youtubeObject = youtubeObject.streams.get_highest_resolution()
    try:
        youtubeObject.download()
    except:
        message.Label.Config(Text = "Some Error Occured, Please try again!")
    message.config(text = "Task Completed")

root = tk.Tk()
root.title("Youtube MP4 Downloader")

userInput = tk.StringVar()

LinkLabel = tk.Label(root, text = "Youtube Link input: ").grid(row = 0, column = 0)
LinkInput = tk.Entry(root, textvariable = userInput, width =45).grid(row = 1, column =0)
message = tk.Label(root, text = "")
message.grid(row = 3, column = 0)  # you need to place this label in the grid as well
ConvertButton = tk.Button(root, text = "Convert to MP4", command=convert).grid(row = 2, column = 0)

root.mainloop()
quit()
print("Done!")
```

## Result
![Fig01](https://github.com/psungg/Python-GUI-Mp4-downloader/blob/main/Images/Fig01.png)

![Fig02](https://github.com/psungg/Python-GUI-Mp4-downloader/blob/main/Images/Fig02.png)

![Fig03](https://github.com/psungg/Python-GUI-Mp4-downloader/blob/main/Images/Fig03.png)

![Fig04](https://github.com/psungg/Python-GUI-Mp4-downloader/blob/main/Images/Fig04.png)
