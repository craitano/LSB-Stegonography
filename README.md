# LSB Stegonography
A LSB  steganography tool for finding hidden messages in PNG files

## Instructions
This will get you started using the LSB Stegonography tool

### Prerequisites
* Python 3

### Running the Script
The general usage is as follows:
```
$ lsbsteg <filename> [Options]...
```
Example: 
```
$ lsbsteg my_img.png
```
This will attempt to find encoded data in the red, green and blue color channels as well as in a combined rgb channel

### Optional arguments
#### At most one of the following options can be specified

* -r

  Process only the red channel
* -g

  Process only the green channel
* -b

  Process only the blue channel
* -a

  Process only the alpha channel
* -rgba

  In addition to the default r, g, b and rgb channels, also process the a channel and a combined rgba channel

Example:
```
$ lsbsteg my_img.png -a
```
This will process only the alpha channel
#### Additionally these arguments can be used or ommitted
* -s
 
  Use this to save all outputs as images with 1s encoded as white pixels and 0s encoded as black pixels
  The image will be saved as <num>_<filename> where num refers to a specific color channel (0: red, 1: green, 2: blue, 3: alpha)
  Example:
  ```
  $ lsbsteg my_img.png -a -s
  ```  
  The will save an image representing the least significant bits of the alpha channel
* -f
  Use this to flip the bits of the decoded message
  
## Author
**Chris Raitano**

## License
This project is licensed under the GPL - see the [LICENSE](LICENSE) file

## Troubleshooting
If the directory containing the lsbsteg script is not specified in your path variable a filepath must be included
* Example using a relative filepath:
  ```
  $ ./lsbsteg my_img.png
  ```
* Example using an absolute filepath:
  ```
  $ /home/user/lsbsteg my_img.png
  ```
If script is not executable you can either change the permissions or run it with the python command
* Changing permissions
  ```
  $ sudo chmod +x lsbsteg
  $ lsbsteg my_img.png
  ```
  or
* Running with python command
  ```
  $ python lsbsteg my_img.png
  ```
