### `UILabel` setup text without change size
```swift
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
