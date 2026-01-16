Problem Description

-An image file was provided as part of the challenge.
-No visible flag was present when viewing the image normally.
-The instructions mentioned analyzing the image at the binary / hexadecimal level.
-The objective was to extract the hidden flag.

Approach

-I first navigated to the challenge directory using WSL.
-Verified the file type using the file command to confirm it was a valid image.
-Checked for readable text inside the image using strings, which did not reveal the full flag.
-Since the challenge required binary analysis, I viewed the image in hexadecimal format using xxd.
-While scrolling through the hex dump, I focused on the ASCII (right) column.
-Near the end of the file, I noticed readable text embedded within the binary data.
-The ASCII column clearly revealed the flag in plain text.

Tools Used

-ls – to verify files in the directory
-file – to confirm the file type
-strings – to search for readable text
-xxd – to view and analyze the file in hexadecimal format
-made proper notes for this and more.

Final Answer : flag{jai-mahismathi}
