# ch7-python-group
"""
Program Name: sepia_chipmunk.py
Authors: Heather Erickson & McKenzie Kowarsch

Program imports image file titled "chipmunk.gif", first converts it to grayscale, then to sepia.


"""

from images import Image

def grayscale(i):
    for y in range(i.getHeight()):
        for x in range(i.getWidth()):
            (r, g, b) = i.getPixel(x, y)
            r = int(r * 0.299)
            g = int(g * 0.587)
            b = int(b * 0.114)
            lum = r + g + b
            i.setPixel(x, y, (lum, lum, lum))
    return(i)
    
def sepia(grayPic):
    for y in range(grayPic.getHeight()):
        for x in range(grayPic.getWidth()):
            (red, green, blue) = grayPic.getPixel(x, y)
            if red < 63:
                red = int(red * 1.1)
                blue = int(blue * 0.9)
            elif red < 192:
                red = int(red * 1.15)
                blue = int(blue * 0.85)
            else:
                red = min(int(red * 1.08), 255)
                blue = int(blue * 0.93)
            grayPic.setPixel(x, y, (red, green, blue))
    return(grayPic)

def main():
    i = Image("chipmunk.gif")
    grayPic = grayscale(i)
    print("Close the image window to continue. ")
    grayPic.draw()
    sepiaPic = sepia(grayPic)
    sepiaPic.draw()
    


if __name__ == "__main__":
    main()
