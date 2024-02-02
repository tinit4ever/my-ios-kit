### `UIButton` setup title with color
```Swift
extension UIButton {
    func setTitle(title: String, color: UIColor) {
        self.setTitle(title, for: .normal)
        self.setTitleColor(color, for: .normal)
        self.setTitleColor(.darkGray, for: .highlighted)
    }
}
```

### `UIButton` setup title font and size
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
```

#### Copyright &#169; 2024 tinit4ever 
