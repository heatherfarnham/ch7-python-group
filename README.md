# ch7-python-group
"""



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

def sepia(t, x, y):
  (red, green, blue) = i.getPixel(x, y)
  if red < 63:
    red = int(red * 1.1)
    blue = int(blue * 0.9)
  elif red < 192:
    red = int(red * 1.15)
    blue = int(blue * 0.85)
  else:
    red = min(int(red * 1.08), 255)
    blue = int(blue * 0.93)
   return



def main():
    i = Image("chipmunk.gif")
    print("Close the image window to continue. ")
    i.draw()
    grayscale(i)
    print("Close the image window to quit. ")
    #sepia(t, 0, 0) 
    i.draw()


if __name__ == "__main__":
    main()
