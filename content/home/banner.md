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
    - title: 👋 Welcome to the CemrgApp page
      content: Slide to download our latest stable release...
      align: center
      background:
        position: right
        color: '#666'
        brightness: 0.7
        media: coders.jpg
    - title: Download Linux
      content: ''
      align: left
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: contact.jpg
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
        media: contact.jpg
      link:
        icon: apple
        icon_pack: fab
        text: Catalina
        url: https://github.com/CemrgAppDevelopers/CemrgApp/releases/download/v2.2/CemrgApp-macOS-v2.2.dmg
    - title: Download Windows
      content: ''
      align: right
      background:
        position: center
        color: '#555'
        brightness: 0.7
        media: contact.jpg
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
        media: contact.jpg
      link:
        icon: github
        icon_pack: fab
        text: Project
        url: https://github.com/CemrgAppDevelopers/CemrgApp
---
