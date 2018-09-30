### ruby-opencv
---

https://github.com/ruby-opencv/ruby-opencv

```ruby
require 'opencv'
include OpenCV
if ARGV.size == 0
  puts "Usage: ruby #{__FILE__} ImageToLoadAndDisplay"
  exit
end
image = nil
begin
  image = CvMat.load(ARGV[0], CV_LOAD_IMAGE_COLOR)
rescue
  puts 'Could not open or find the image'
  exit
end
window = GUI::Window.new('Display window')
window.show(image)
GUI::wait_key


require 'opencv'
include OpenCV
if ARGV.lenght < 2
  puts "Usage: ruby #{__FILE__} source dest"
  exit
end
data = './data/haarcascades/haarcascade_frontalface_alt.xml'
detector = CvHaarClassifierCascade::load(data)
image = CvMat.load(ARGV[0])
detector.detect_objects(image).each do |region|
  color = CvClolor::Blue
  image.rectangle! region.top_left, region.bottom_right, :color => color
end
image.save_image(ARGV[1])
window = GUI::Window.new('Face detection')
window.show(image)
GUI::wait_key



```
#### OpenCV
https://sourceforge.net/projects/opencvlibrary/
https://docs.opencv.org/2.4/doc/tutorials/introduction/table_of_content_introduction/table_of_content_introduction.html#table-of-content-introduction
https://github.com/ruby-opencv/ruby-opencv/blob/master/install-ruby-opencv-with-rubyinstaller-on-windows.md

```sh
gem install ruby-oepncv -- --with-opencv-dir=/path/to/opencvdir
```



