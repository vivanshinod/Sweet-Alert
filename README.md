# Sweet-Alert

Cool Libarary for alert dialog

1) simple dialog
_ = SweetAlert().showAlert("Hello World!")

2) title with a text under

SweetAlert().showAlert("Here's a message!", subTitle: "It's pretty, isn't it?", style: AlertStyle.None)

3) Animated Success message：

SweetAlert().showAlert("Good job!", subTitle: "You clicked the button!", style: AlertStyle.Success)

4) Warning message and Chained Animated Success messge on completion:

SweetAlert().showAlert("Are you sure?", subTitle: "You file will permanently delete!", style: AlertStyle.Warning, buttonTitle:"Cancel", buttonColor:UIColorFromRGB(0xD0D0D0) , otherButtonTitle:  "Yes, delete it!", otherButtonColor: UIColorFromRGB(0xDD6B55)) { (isOtherButton) -> Void in
            if isOtherButton == true {
            
                println("Cancel Button  Pressed")
            }
            else {
                SweetAlert().showAlert("Deleted!", subTitle: "Your imaginary file has been deleted!", style: AlertStyle.Success)
            }
}

5) Chained Alerts on actions with custom button colors:

//Chaining alerts with messages on button click
SweetAlert().showAlert("Are you sure?", subTitle: "You file will permanently delete!", style: AlertStyle.Warning, buttonTitle:"No, cancel plx!", buttonColor:UIColorFromRGB(0xD0D0D0) , otherButtonTitle:  "Yes, delete it!", otherButtonColor: UIColorFromRGB(0xDD6B55)) { (isOtherButton) -> Void in
            if isOtherButton == true {
                
                SweetAlert().showAlert("Cancelled!", subTitle: "Your imaginary file is safe", style: AlertStyle.Error)
            }
            else {
                SweetAlert().showAlert("Deleted!", subTitle: "Your imaginary file has been deleted!", style: AlertStyle.Success)
            }
}

6) Custom icon alert:

SweetAlert().showAlert("Sweet!", subTitle: "Here's a custom image.", style: AlertStyle.CustomImag(imageFile: "thumb.jpg"))

7) Diffrent Animated Styles for Diffrent Purposes:

enum AlertStyle {
    case Success,Error,Warning,None
    case CustomImag(imageFile:String)
}
