Title: Linux Howto's
Subtitle: Handy tips and tricks and answers to common questions
Date: 2016-01-12



## How to add text to the BEGINNING of a file

```bash
echo -e "task goes here\n$(cat todo.txt)" > todo.txt
```

[More info](http://superuser.com/questions/246837/how-do-i-add-text-to-the-beginning-of-a-file-in-bash)
