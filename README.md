CCValidatedTextField
====================

Add real-time validation to UITextField with blocks

![sample](http://i.imgur.com/Gy8Ylvs.gif)

Easy block based methods with the opportunity for full customization

    NSString *emailPattern = @"^[_a-z0-9-]+(\\.[_a-z0-9-]+)*@[a-z0-9-]+(\\.[a-z0-9-]+)*(\\.[a-z]{2,4})$";
    _emailField.validationBlock = ^(NSString *text) {
      return ([text rangeOfString:emailPattern options:NSRegularExpressionSearch].location != NSNotFound );
    };
    _emailField.postValidationBlock = ^(BOOL valid){
      if ( valid ) {
        _emailStatus.image = [UIImage imageNamed:@"valid"];
      } else {
        _emailStatus.image = [UIImage imageNamed:@"invalid"];
      }
    };

If you want to check if a textfield is currently valid (before submitting a form, for example), simply check CCTextField's .valid property

    BOOL fieldIsInValidState = _emailField.valid;



##Installation##
Cocoapods

    pod 'CCValidatedTextField', '~> 1.0.1'
