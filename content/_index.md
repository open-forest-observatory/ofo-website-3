---
# Leave the homepage title empty to use the site title
title:
type: landing
profile: false

sections:
  - block: markdown
    design:
      background:
        image:
          filename: featured-background.jpg
          filters:
            brightness: 0.75
          parallax: false
          position: top
          size: cover
        text_color_light: true
      spacing:
        padding: ["80px", "10px", "10px", "10px"]
      css_class: fullscreen
    content:
      title: 
      text: |

        <div class="container">
        <div class="row justify-content-center">
        <div class="col-xl-10">
        <div style="text-align: center; font-size: 225%; line-height: 120%;">

        **Drone-based mapping for**
        
        **Forest Ecology and Management**

        </div>
        <br>
        <img src="log0.png#tester" width="175" class="tester">
        <b class="tester" style="font-size: 120%">Open Forest Observatory</b>
        
        <br>
        <br>

        <div style="text-align: center; font-size: 275%; line-height: 120%;">
        <i class="fas fa-circle-down"></i>
        </div>

        </div>
        </div>




  - block: markdown
    design:
      background:
        color: "#30638e"
        text_color_light: TRUE
    content:
      text: |

        <div class="container">
        <div class="row justify-content-center">
        <div class="col-xl-10">

        The Open Forest Observatory, a collaboration across universities and other partners, is working to make low-cost, AI-enabled drone-based forest mapping accessible to ecologists, land managers, and the general public.

        The OFO tools in development will be usable by groups and individuals with limited background in drones and remote sensing. All of our work is open-source (see our work on [GitHub](https://github.com/open-forest-observatory)). We are keen to collaborate with anyone interested in using and/or contributing to our tools. Learn how to [contact us](/about/#contact).

        </div>
        </div>
        </div>



  - block: markdown
    # design:
    #   # background:
    #   #   color: "#30638e"
    #   #   text_color_light: TRUE
    design:
      spacing:
        padding: ["10px", "10px", "30px", "10px"]
    content:
      text: |
        <div class="container">
        <div class="row justify-content-center">
        <div class="col-xl-10">
        
        <div class = "tester">
        
        # OFO resources

        </div>

        </div>
        </div>
        
        <div class="row">
        <div class="col-sm">
        <div class="text-center">
        <i class="fa-solid fa-map-location fa-3x" style="margin-top: 0.5em;"></i>
        <h3 style="margin-top: 1em;">Forest map data</h3>
        <p>We host databases of <a href="/data/drone/">drone-derived data</a> and <a href="/data/ground-ref/">traditional field-based data </a> at the same sites, along with guidelines for others wishing to collect their own data.</p>

        [Data >](/data/)
        </div>
        </div>

        <div class="col-sm">
        <div class="text-center">
        <i class="fa-solid fa-compass-drafting fa-3x" style="margin-top: 0.5em;"></i>
        <h3 style="margin-top: 1em;">Forest mapping tools</h3>
        <p>We develop and support easy-to-use tools to allow users to process their own drone imagery into individual-tree forest maps using current best-practices as defaults.</p>

        [Tools >](/tools/)


---
