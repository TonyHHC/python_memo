## 出現 ../../../src/utils/typeconv.cpp:529:5: error: ‘wxFALLTHROUGH’ was not declared in this scope
### 解决方法
```
找到typeconv.cpp文件，将其中所有的wxFALLTHROUGH删除即可
```

## 对‘uuid_generate@UUID_1.0’未定义的引用
### 解决方法
```
ldd /usr/lib/x86_64-linux-gnu/libSM.so.6
rm -rf /home/tony/anaconda3/lib/libuuid.so.1
ln -s /lib/x86_64-linux-gnu/libuuid.so.1 /home/tony/anaconda3/lib/libuuid.so.1
```

## 執行時出現 Error loading library /home/…/wxFormBuilder/_install/lib/.....
### 解决方法
```
make 完後 cd 到 _install/lib 下  
將所需 lib move 到正確位置
```
