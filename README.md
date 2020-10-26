# ch7-python-group

(red, green, blue) = image.getPixel(x, y)
if red < 63:
  red = int(red * 1.1)
  blue = int(blue * 0.9)
elif red < 192:
  red = int(red * 1.15)
  blue = int(blue * 0.85)
else:
  red = min(int(red * 1.08), 255)
  blue = int(blue * 0.93)
