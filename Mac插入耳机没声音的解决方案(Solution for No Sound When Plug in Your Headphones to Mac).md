##Mac插入耳机没声音的解决方案(Solution for No Sound When Plug in Your Headphones to Mac)

最近遇到了两次电脑（RMBP）插入耳机后耳机无声的问题，第一次重启解决，第二次不想重启，在做了一番搜索尝试后，最终的有效方案是重新加载下驱动。在终端执行如下命令即可：

```
sudo kextunload /System/Library/Extensions/AppleHDA.kext
sudo kextload /System/Library/Extensions/AppleHDA.kext
```

希望可以帮到有类似烦恼的人。



##Solution for No Sound When Plug in Your Headphones to Mac

Recently met twice headphones silent problem when plug in my Headphones to my RMBP.  I solved the first one with a reboot, but I don't want to reboot the second time. I did some google, the final effective solution is to reload the drive. Run the following command in terminal fix my issue:

```
sudo kextunload /System/Library/Extensions/AppleHDA.kext
sudo kextload /System/Library/Extensions/AppleHDA.kext
```

Hope this can help you.
