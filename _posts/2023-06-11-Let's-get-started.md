---
layout: post
date: 2023-06-11
title: Let's get started!
---

# My thank you

First of all, I want to say thanks to Mr.Xeno, who created a lot of courses for reverse engineering and this first post will be about the  **Binary_Bomb_lab** the lab for a beginer like me.
You also can find course via this link: https://p.ost2.fyi/

# Now let's start the **Binary_Bomb_lab**

## Introduce the bomb_lab

This is the most assembly exercise and I think I'll get my first step on this, about the detail of this binary, please watch via this: [bomb_lab_intro](https://p.ost2.fyi/courses/course-v1:OpenSecurityTraining2+Arch1001_x86-64_Asm+2021_v1/courseware/5dc2d5b3af5d4b4b954d30fd5f772de2/0e7a4214a53f4f0da5060f9d221adbd4/?activate_block_id=block-v1%3AOpenSecurityTraining2%2BArch1001_x86-64_Asm%2B2021_v1%2Btype%40sequential%2Bblock%400e7a4214a53f4f0da5060f9d221adbd4)

## Bomb_lab

I think I'll try a little bit different from the guide of Mr.Xeno, I'm a lazy man so I'll try with **Ghidra**.

### Phase 1

I took a look on the function/main/main then here we go, **Let's the hunt beginnnnn**

The Phases will be called through this![image](https://github.com/br0k4n/br0k4n.github.io/assets/136005668/c1d977e1-ae16-4e98-b4e7-e096df774bba)

```
  printf("Welcome to my fiendish little bomb. You have 6 phases with\n");
  printf("which to blow yourself up. Have a nice day!\n");
  input = read_line();
  phase_1(input);
  phase_defused()
  ```
I saw that `phase_1(input)`, let have a look at that.
![image](https://github.com/br0k4n/br0k4n.github.io/assets/136005668/0b32df21-33e3-428f-ba8e-d61dadd4b2dd)

We saw the function named `strings_not_equal` then I knew that will be compare to second argument. We had `TEST EAX, EAX` and `JZ LAB_140012062` so if the ZeroFlag is set, then we can go to the next phase. Just dig in then you could saw the strings to get into Phase_2.
