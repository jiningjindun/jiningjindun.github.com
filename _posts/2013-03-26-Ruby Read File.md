---
layout: post
title: "Ruby简单读取文件 "
description: ""
category: Ruby
tags: [ruby]
---
{% include JB/setup %}


(1)用于获取键盘输入，并输出
 
Ruby代码  
while line = gets  
    puts line  
end  
 
 (2)按照行读取文件内容
 
Ruby代码  
File.open("E:/workspaceNew/RubyStudy/test.txt") do |file|  
file.each_line{|line| puts "Got #{line.dump}"}  
 
end  
 
 (3)按照行读取文件，并按照制定的字符串进行分割.本文中以e字母进行分割
 
Ruby代码  
File.open("E:/workspaceNew/RubyStudy/test.txt") do |file|  
file.each_line("e"){|line| puts "Got #{line.dump}"}  

end  
 
 (4)使用IO.foreach读取文件
 
Ruby代码  
IO.foreach("E:/workspaceNew/RubyStudy/test.txt"){|line| puts line};  
 
 (5)可以将读取的文件保存在一个字符串当中
 
Ruby代码  
str = IO.read("E:/workspaceNew/RubyStudy/test.txt");  
  puts str.length;  
  puts str[0,30]  
 
 (6)也可以将读取的文件保存在一个数组当中
 
Ruby代码  
arr = IO.readlines("E:/workspaceNew/RubyStudy/test.txt")  
puts arr.length;  
puts arr[0]  