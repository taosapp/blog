# Sublime Text 3 sass config
2014-03-24 11:14:00

## first install sass and sass build plugin，create a test.scss file
```css
$color: #369;
body {
    background: darken($color, 10%);
}
```

press Ctrl+B to compile, if successfully：
```bash
write C:\Users\work/test.css [Finished in 0.8s]
```

## if error
```bash
Decode error - output not utf-8
……
```
press your right mouse button on `My Computer`, select `Property -> Advanced or Advanced System Settings(win8.1)`, click the `Advanced` tab, then click the `Environment Variables` button near the bottom of that tab, in the `System variables` section and click the `Edit` button. Add your ruby bin path, such as:

>C:\AppServ\php5;C:\AppServ\MySQL\bin;C:\Ruby200-x64\bin

Then restart Sublime Text 3, open test.scss, press Ctrl+B again