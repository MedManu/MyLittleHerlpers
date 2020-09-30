1. Git:
   1. Develop branch auschecken u pullen
   2. neuen branch für release erstellen (git checkout -b iOS-version)
   3. git log u git diff für Unterscheide
   4. neuen Branch commiten (git commit -a -m"bump version 1.2.2")
   5. neue version pushen git push -u / git push --set-upstream origin namedesBranches
2. Xcode
   1. Version u Build number erhögen um 1
   2. Generic IOS device als simulator auswählen
   3. Product - Archive (alles so lassen wie es ist)
   4. Upload to App Store

https://www.raywenderlich.com/5352-testflight-tutorial-ios-beta-testing