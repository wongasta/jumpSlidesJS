#JumpSlides.JS
###version 1.0.0
###author: Yixin Xia

The library contains the following files

* jumpSlides.js - main library JS file
* jumpSlides.min.js - minimized main library JS file
* /img - dir that contains all the images that is used. Can be redefined to another folder in config object
* bower.json - manages the package and dependencies the user can pull
* example.html - contains example HTML file with comments - show how it's populated
* /_css - not needed: contains bootstrap styles for the example.html
* /_js - contains all the dependencies of the library
* /bower_components - contains all the dependencies of the library bower pulls


Library dependencies. This library requires the following libraries in the following order

* JQuery (>=1.2)
* JQuery UI (>=1.10.3)
* jQuery Waypoints (>=2.0.4)

This library come packaged with bower.json, which you can use the following commands to retrieve the latest dependency library

```
bower-installer install
```

If bower and bower-installer is not on your computer you can

```
npm install -g bower
npm install -g bower-installer
```

To initialize the library on your Div just do the following. Just make sure you have defined the config object somewhere already.

```
$('#yourDiv').populateShowcase(config);
```

Below is an example of config object you can pass in with commentaries on all the properties you can customize.

```
//Declare the main JSON configuration. All properties below are NEEDED - not optional to exclude (which might change on future releases).
    var config = {
        //The height of the container Div
        'containerHeight': 850,
        //Defines the maximum width of the window for it to be on mobile mode
        'mobileResWidth': 400,
        //The height of the container Div when in mobile mode
        'mobileContainerHeight': 550,
        //Horizontal margin of each columns
        'horzMargin': 20,
        //Horizontal margin of each columns on mobile
        'mobileHorzMargin': 20,
        //CSS border property of each of the images
        'imgBorder': '1px solid #dbdbdb',
        //The Y offset value for waypoint.jquery - higher the number the higher up on the page this library will animate
        'wpYOffset': 720,
        //The size reduction multiplier in mobile mode. For example 100px x 100px of an image with 0.5 mobileImgReduce will be 50px x 50px in mobile
        'mobileImgReduce': 0.5,
        //How many pixels each column will glide up/down upon user scroll
        'mobileImgScrollRate': 2,
        //Contains all the metadata of all the images you plan to use in this library
        'picInfo': {
            //Directory of where you kep the pictures. Currently all images must be in the same directory.
            'picDir': 'img/',
            'picList':{
                //Assign each picture with an unique value, which you can use throughout the code
                'picAdventure': 'volusion_adventure_250x450.jpg',
                'picKoenig': 'volusion_koenig_250x350.jpg',
                'picLux': 'volusion_lux_250x225.jpg',
                'picHeadfirst': 'volusion_headfirst_250x450.jpg',
                'picBeautybox': 'volusion_beautybox_250x350.jpg',
                'picSoundscape': 'volusion_soundscape_250x225.jpg',
                'picStevenson': 'volusion_stevenson_250x450.jpg',
                'picDahlia': 'volusion_dahlia250x350.jpg',
                'picPaper': 'volusion_paper_250x225.jpg',
                'picVestitos': 'volusion_vestitos_250x450.jpg',
                'picReverb': 'volusion_reverb_250x350.jpg'
            }
        },
        //Define each columns in mobile
        'mobileCol': [
            //Column 1
            {
                //Vertical margin in between each picture
                'vertMargin': 10,
                //List of each pictures you want to use in mobile mode - name is derived rom picList above
                'pics': [
                    //1st picture in the column
                    {
                        'name': 'picBeautybox'
                    },
                    //2nd picture in the column
                    {
                        'name': 'picKoenig'
                    },
                    //3rd picture in the column
                    {
                        'name': 'picHeadfirst'
                    },
                    //4th picture in the column
                    {
                        'name': 'picLux'
                    },
                    //5th picture in the column
                    {
                        'name': 'picAdventure'
                    }
                ]
            },
            //Column 2
            {
                'vertMargin': 10,
                'pics': [
                    {
                        'name': 'picReverb'
                    },
                    {
                        'name': 'picDahlia'
                    },
                    {
                        'name': 'picPaper'
                    },
                    {
                        'name': 'picStevenson'
                    },
                    {
                        'name': 'picVestitos'
                    }
                ]
            }
        ],
        //Assign pictures in each column for non mobile mode
        'col': [
            //Column 1
            {
                //Animation effects you can use from JQuery UI
                //http://api.jqueryui.com/easings/
                'animationTimeFunc': 'easeInExpo',
                //How long it will take for each column to be slided up
                'animationTimer': 500,
                //How long it will take each column to bounce after it's slided up
                'bounceTimer': 500,
                //How many times the library will make the column bounce
                'bounceAttempts': 1,
                //How far in pixels will the columns bounce
                'bounceDistance': 100,
                //Delay for this column before it does any animation
                'animationDelay': 0,
                //How many pixels will the column be offsetted down. Higher value means the column will be shorter and pushed down
                'animationYOffset': 160,
                //Margin-bottom on each picutres in the column
                'vertMargin': 20,
                //If the user's window width is lesser than the value below, this column will be hidden
                'responsiveHideLessThan': 768,
                //Array of list of pics you want to use for the column
                'pics': [
                    //1st img
                    {
                        'name': 'picAdventure'
                    },
                    //2nd img
                    {
                        'name': 'picKoenig'
                    }
                ]
            },
            //Column 2
            {
                'animationTimeFunc': 'easeInExpo',
                'animationTimer': 500,
                'bounceTimer': 500,
                'bounceAttempts': 1,
                'bounceDistance': 100,
                'animationDelay': 100,
                'animationYOffset': 140,
                'vertMargin': 20,
                'responsiveHideLessThan': -1,
                'pics': [
                    {
                        'name': 'picLux'
                    },
                    {
                        'name': 'picHeadfirst'
                    }
                ]
            },
            //Column 3
            {
                'animationTimeFunc': 'easeInExpo',
                'animationTimer': 500,
                'bounceTimer': 500,
                'bounceAttempts': 1,
                'bounceDistance': 100,
                'animationDelay': 500,
                'animationYOffset': 100,
                'vertMargin': 20,
                'responsiveHideLessThan': -1,
                'pics': [
                    {
                        'name': 'picBeautybox'
                    },
                    {
                        'name': 'picSoundscape'
                    }
                ]
            },
            //Column 4
            {
                'animationTimeFunc': 'easeInExpo',
                'animationTimer': 500,
                'bounceTimer': 500,
                'bounceAttempts': 1,
                'bounceDistance': 100,
                'animationDelay': 700,
                'animationYOffset': 80,
                'vertMargin': 20,
                'responsiveHideLessThan': 768,
                'pics': [
                    {
                        'name': 'picStevenson'
                    }
                ]
            },
            //Column 5
            {
                'animationTimeFunc': 'easeInExpo',
                'animationTimer': 500,
                'bounceTimer': 500,
                'bounceAttempts': 1,
                'bounceDistance': 100,
                'animationDelay': 200,
                'animationYOffset': 130,
                'vertMargin': 20,
                'responsiveHideLessThan': -1,
                'pics': [
                    {
                        'name': 'picDahlia'
                    },
                    {
                        'name': 'picPaper'
                    }
                ]
            },
            //Column 6
            {
                'animationTimeFunc': 'easeInExpo',
                'animationTimer': 500,
                'bounceTimer': 500,
                'bounceAttempts': 1,
                'bounceDistance': 100,
                'animationDelay': 0,
                'animationYOffset': 160,
                'vertMargin': 20,
                'responsiveHideLessThan': 768,
                'pics': [
                    {
                        'name': 'picVestitos'
                    },
                    {
                        'name': 'picReverb'
                    }
                ]
            }
        ]
    };
```