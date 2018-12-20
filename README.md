# CarMarker-Animation
[![](https://jitpack.io/v/tintinscorpion/CarMarker-Animation.svg)](https://jitpack.io/#tintinscorpion/CarMarker-Animation)

<br>
<meta name="google-site-verification" content="9xX5qBXiwU0-eOti0o3ujCSFXmus9BTbz6Dw5FNmtm0" />
Smooth marker animation on google map along with proper turns and camera bearing. 
<br><br>

# Demo
<img src="https://github.com/tintinscorpion/CarMarker-Animation/blob/master/routeanim.gif"/>

<br><br>

## Steps:
<UL>
<LI>Pass the Marker to animate, googlemap, Latlng of current position of the marker, Latlng of curent position of the user, 
 duration of the animation & Cancellable Callback interface of googlemap.
<pre>
<code>
<LI>CarMoveAnim.startcarAnimation(marker,googleMap, startposition,endposition,duration,callback);
</LI>
<br><br>
Here marker,googlemap,startposition refers to the position of marker,end position refers to the position of 
the user or wherever the marker needs to be placed. 
These four fields are mandatory.
<br><br>
<LI>Optional:
<pre>
duration refers to the animation time. By default it will take 3000 even if 0 is passed.
callback is the interface of Googlemap.CancellabeCallback(). It requires when the user wants to animate the next animation 
after the first has finished else just pass null.
<br>
For eg-
<code>
new GoogleMap.CancelableCallback() {
                @Override
                public void onFinish() {                
                }
                @Override
                public void onCancel() {               
                }
            });
</code>
</pre>
</LI>
</code>
</pre>
</LI>
 <LI>
  <ul>Note:
   <code>
    If you are animating car onLocationChanged() then,
   Ideal location request for car animation should be as below. Greater than the interval mentioned will give
   more good results but less than this may hamper the animation.

    mLocationRequest = new LocationRequest();
    mLocationRequest.setInterval(1000 * 5);
    mLocationRequest.setFastestInterval(1000 * 3);
    mLocationRequest.setPriority(LocationRequest.PRIORITY_HIGH_ACCURACY);
    
   </code>
 </LI>

## Dependency
<pre>
<LI>App Level:
implementation 'com.github.tintinscorpion:CarMarker-Animation:1.1'
</LI>
<br>
<LI>Project Level:
maven { url 'https://jitpack.io' }
</LI>
</pre>


# Developers
<UL>
<LI><a href="https://github.com/tintinscorpion">Pritam Dasgupta</a>
</UL>

## License

  <code>
 MIT License

Copyright (c) 2018 Pritam Dasgupta

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
  </code>
