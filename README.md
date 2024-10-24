# Unicornshredder2writeup
FOI CTF - Unicorn Shredder 2.0 pre-challenge 2024 WRITEUP


From this video; https://www.youtube.com/watch?v=PmbAmHExJls
A pre-challenge for CrateCTF2024, FUN!
Link to the shredder; https://shredder.crate.foi.se/

<hr>

**Description**
A webpage that destroys images that are uploaded to it.
Find the flag!

<hr>

**How i did it**

1. Test how it destorys the image.
    First i tested in the scissor friendly and relized that it was not going to show the flag.
     The scissor friendly images in the shred bucket, did not seem to show the flag...
     I did try to piece together one of the images as a puzzle;
   ![Skärmavbild 2024-10-23 kl  14 18 47](https://github.com/user-attachments/assets/51ead3cb-f2cc-4d47-bdb4-f9e96c84caf4)
 
   I made a random image to test how the "ultra secure" i destorys the image, i made this;
   ![test2](https://github.com/user-attachments/assets/7261718c-2834-4fb3-a23a-ce7ef63815a8)
   Shredded it thru "ultra secure" and got this;
   ![image](https://github.com/user-attachments/assets/0b18aa50-e210-4bd0-86a6-a6c0925e8067)

   It seems to only shred on the width...
   To try the theory i made this image;
   ![test4](https://github.com/user-attachments/assets/ed05ef42-cd43-41d0-85a8-8ab85e8d98a7)
    This was to see if it only shifts to the side. The Results confirmed it;
   ![image](https://github.com/user-attachments/assets/75d66f2c-9580-4b36-9dbf-8017cea45215)

2. Guess what image contains a flag 
    I check thru how last years shredder challenge was solved and in that challenge it was one of the first images in the shred bucket
   so i took the first ultra securly shredded image in the shred bucket, this one;
   ![image](https://github.com/user-attachments/assets/56d898fe-6990-49cb-8dd2-a5ed50d95139)

3. I checked the standard, exiftool, binwalk and stuff like that. Nothing there.
4. I then checked the pixel width on the shred slices in the image from the shred bucket 1px
     Took a little insperation from on how last years challenge was solved

5. Wrote a python script that shredded the image widthways into multible images
    Here is the script; https://github.com/SadEmoji/Python_scripts/blob/main/Image_slicer.py
    This script gave me 800 imagefiles that are 1x600px
   
6. I first tried a script that put together the image slices into random images...
   Thought dumb luck is still luck.
   I did not work. You can find this script on my github.

7. I tought that because its only two colors in the image i may be able to pixelsort it!
   I wanted to sort it so white pixels needs to touch other white pixels.
   Wrote a script for that, this one; https://github.com/SadEmoji/Python_scripts/blob/main/Image_arrange_sort_color.py

8. Success!
   Somthing that is somewhat readable
  ![1](https://github.com/user-attachments/assets/efcc8c5e-75cb-491f-8d91-485d7b8db7fa)

9. Opened the image in a image-manipulator software, like gimp.
    Re arranged the image

10. chuckled at the irony.

There was no real way to submit the flag so i just confirmed it on the discord.
  

    


