# Welcome to My iOSKit

## In this repository you will find:
* My customize code for iOS development that I stored to reuse and reference

### 1. UIKit
- **Set bold `UILabel` text without change size**  
```Swift
extension UILabel {
    func setBoldText() {    
        if let currentFont = self.font {
            let boldFont = UIFont(descriptor: currentFont.fontDescriptor.withSymbolicTraits(.traitBold)!, size: currentFont.pointSize)
            self.font = boldFont
        }
    }
}
```

#### Copyright &#169; 2024 tinit4ever
