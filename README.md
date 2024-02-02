# Welcome to My iOSKit

## In this repository you will find:
* My customize code for iOS development that I stored to reuse and reference

### 1. UIKit
- **`UILabel` setup text without change size**  
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

- **`UIButton` setup title with color**
```Swift
extension UIButton {
    func setTitle(title: String, color: UIColor) {
        self.setTitle(title, for: .normal)
        self.setTitleColor(color, for: .normal)
        self.setTitleColor(.darkGray, for: .highlighted)
    }
}
```

- **`UIButton` setup title font and size**
```Swift
extension UIButton {
    func setTitle(fontName: String, size: CGFloat) {
        var configuration = self.configuration ?? UIButton.Configuration.gray()
        configuration.titleTextAttributesTransformer =
        UIConfigurationTextAttributesTransformer { incoming in
            var outgoing = incoming
            outgoing.font = UIFont(name: fontName, size: size)
            
            if let descriptor = outgoing.font?.fontDescriptor {
                outgoing.font = UIFont(descriptor: descriptor.withSymbolicTraits(.traitBold)!, size: size)
            }
            
            return outgoing
        }
        
        self.configuration = configuration
    }
}

#### Copyright &#169; 2024 tinit4ever
