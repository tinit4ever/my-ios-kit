### Show Password Button
- **Setup this for create `ShowPasswordButton`:**
```Swift
extension UIButton {
    func showPasswordButton() {
        self.setImage(UIImage(systemName: SystemImageNames.eyeSlash), for: .normal)
        self.tintColor = .systemGray
    }
}
```

- **Use this for set button position:**
```Swift
extension UITextField {
    func showPasswordButton(showPasswordButton: UIButton) {
        self.rightView = showPasswordButton
        self.rightViewMode = .always
    }
}
```

- **This is implements:**  
```Swift
// Init components
lazy var passwordTextField = UITextField()
lazy var showPasswordButton = UIButton()
```

```Swift
// Config needed appreances
showPasswordButton.showPasswordButton()

passwordTextField.isSecureTextEntry = true
```

```Swift
// Add target acction
showPasswordButton.addTarget(self, action: #selector(togglePasswordVisibility), for: .touchUpInside)
```

```Swift
// Config password onlick
@objc
private func togglePasswordVisibility() {
    passwordTextField.isSecureTextEntry.toggle()
    let eyeSymbol = passwordTextField.isSecureTextEntry ? "eye.slash" : "eye"
    if let showPasswordButton = passwordTextField.rightView as? UIButton {
        showPasswordButton.setImage(UIImage(systemName: eyeSymbol), for: .normal)
    }
}
```


#### Copyright &#169; 2024 tinit4ever 
