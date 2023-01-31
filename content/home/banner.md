---
widget: slider
weight: 1
active: true
headless: true

design:
  # Slide height is automatic unless you force a specific height (e.g. '400px')
  slide_height: '250px'
  is_fullscreen: false
  # Automatically transition through slides?
  loop: false
  # Duration of transition between slides (in ms)
  interval: 10000

content:
  slides:
    - title: Welcome
      content: Slide to download our latest stable release...
      align: center
      background:
        position: top
        color: '#666'
        brightness: 0.8
        media: screenshot_scar.png
    - title: Download Linux
      content: ''
      align: center
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: cemrgapp_banner.png
      link:
        icon: ubuntu
        icon_pack: fab
        text: 18.04
        url: https://github.com/CemrgAppDevelopers/CemrgApp/releases/download/v2.2/CemrgApp-Linux-v2.2.zip
    - title: Download macOS
      content: ''
      align: center
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: cemrgapp_banner.png
      link:
        icon: apple
        icon_pack: fab
        text: Catalina
        url: https://github.com/CemrgAppDevelopers/CemrgApp/releases/download/v2.2/CemrgApp-macOS-v2.2.dmg
    - title: Download Windows
      content: ''
      align: center
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: cemrgapp_banner.png
      link:
        icon: windows
        icon_pack: fab
        text: 10
        url: https://github.com/CemrgAppDevelopers/CemrgApp/releases/download/v2.2/CemrgApp-Windows-v2.2.zip
    - title: Code repository
      content: ''
      align: center
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: cemrgapp_banner.png
      link:
        icon: github
        icon_pack: fab
        text: Project
        url: https://github.com/CemrgAppDevelopers/CemrgApp
---
