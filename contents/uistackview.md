# UIStackView

> A streamlined interface for laying out a collection of views in either a column or a row.

For all distributions except the fillEqually distribution, the stack view uses each arranged view’s intrinsicContentSize property when calculating its size along the stack’s axis. fillEqually resizes all the arranged views so they are the same size, filling the stack view along its axis. If possible, the stack view stretches all the arranged views to match the view with the longest intrinsic size along the stack’s axis.  

For all alignments except the fill alignment, the stack view uses each arranged view’s intrinsicContentSize property when calculating its size perpendicular to the stack’s axis. fill resizes all the arranged views so that they fill the stack view perpendicularly to its axis. If possible, the stack view stretches all the arranged views to match the view with the largest intrinsic size perpendicular to the stack’s axis.


```
class ViewController: UIViewController {
    var stackView = UIStackView()
    var nestedStackView = UIStackView()

    override func viewDidLoad() {
        super.viewDidLoad()
        stackView.translatesAutoresizingMaskIntoConstraints=false
        self.view.addSubview(stackView)
        // Main UIStackView contraints, nearly fills its parent view
        self.view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "V:|-30-[stackView]-30-|",options: NSLayoutFormatOptions.alignAllLeading,metrics: nil, views: ["stackView":stackView]))
        self.view.addConstraints(NSLayoutConstraint.constraints(withVisualFormat: "H:|-10-[stackView]-10-|",options: NSLayoutFormatOptions.alignAllLeading,metrics: nil, views: ["stackView":stackView]))

        stackView.axis = .vertical
        stackView.alignment = .fill
        stackView.spacing = 25
        stackView.distribution = .fillEqually

        var lbl = UILabel()
        lbl.text = "Label 1"
        lbl.backgroundColor = UIColor.red
        stackView.addArrangedSubview(lbl)

        lbl = UILabel()
        lbl.text = "Label 2"
        lbl.backgroundColor = UIColor.green
        stackView.addArrangedSubview(lbl)

        nestedStackView.axis = .horizontal
        nestedStackView.alignment = .fill
        nestedStackView.spacing = 25
        nestedStackView.distribution = .fillEqually
        nestedStackView.addArrangedSubview(UIButton(type: .infoDark))
        nestedStackView.addArrangedSubview(UIButton(type: .infoDark))
        nestedStackView.addArrangedSubview(UIButton(type: .contactAdd))
        stackView.addArrangedSubview(nestedStackView)

        let btn = UIButton(type: .system)
        btn.setTitle("Press Me", for: .normal)
        btn.addTarget(self, action: #selector(pressedMe), for: .touchUpInside)
        stackView.addArrangedSubview(btn)
    }

    @objc func pressedMe(){
        UIView.animate(withDuration: 0.5) {
            self.nestedStackView.isHidden = !self.nestedStackView.isHidden
        }
    }
}

```

## REFERENCE
[iOS9 UIStackView 简介](http://swift.gg/2016/03/31/ios9-uistackview-guide-swift/)
