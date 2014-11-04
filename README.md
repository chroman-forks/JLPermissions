# JLPermissions

[![Version](http://cocoapod-badges.herokuapp.com/v/JLPermissions/badge.png)](http://cocoadocs.org/docsets/JLPermissions)
[![Platform](http://cocoapod-badges.herokuapp.com/p/JLPermissions/badge.png)](http://cocoadocs.org/docsets/JLPermissions)

## Requirements

iOS 7.0+

## Installation

JLPermissions is available through [CocoaPods](http://cocoapods.org), to install it simply add the following line to your Podfile:

    pod "JLPermissions/Calendar"
    pod "JLPermissions/Contacts"
    pod "JLPermissions/Facebook"
    pod "JLPermissions/Health"
    pod "JLPermissions/Location"
    pod "JLPermissions/Microphone"
    pod "JLPermissions/Notification"
    pod "JLPermissions/Photos"
    pod "JLPermissions/Reminders"
    pod "JLPermissions/Twitter" 

Only add the pod for the permissions you plan on using.  Apple rejects apps that include Healthkit API's but do not use them.

## Usage

To run the example project; clone the repo, and run `pod install`, then open JLPermissionsExample.xcworkspace.

The method for asking for each type of permission (other than push notifications) is virtually identical.  Here are the core methods from each permissions API header file:

```objective-c

typedef void (^AuthorizationHandler)(bool granted, NSError *error);
typedef void (^NotificationAuthorizationHandler)(NSString *deviceID, NSError *error);

- (BOOL)contactsAuthorized;
- (void)authorizeContacts:(AuthorizationBlock)completionHandler;
- (void)authorizeContactsWithTitle:(NSString *)messageTitle
                           message:(NSString *)message
                       cancelTitle:(NSString *)cancelTitle
                        grantTitle:(NSString *)grantTitle
                 completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)calendarAuthorized;
- (void)authorizeCalendar:(AuthorizationBlock)completionHandler;
- (void)authorizeCalendarWithTitle:(NSString *)messageTitle
                           message:(NSString *)message
                       cancelTitle:(NSString *)cancelTitle
                        grantTitle:(NSString *)grantTitle
                 completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)photosAuthorized;
- (void)authorizePhotos:(AuthorizationBlock)completionHandler;
- (void)authorizePhotosWithTitle:(NSString *)messageTitle
                         message:(NSString *)message
                     cancelTitle:(NSString *)cancelTitle
                      grantTitle:(NSString *)grantTitle
               completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)remindersAuthorized;
- (void)authorizeReminders:(AuthorizationBlock)completionHandler;
- (void)authorizeRemindersWithTitle:(NSString *)messageTitle
                            message:(NSString *)message
                        cancelTitle:(NSString *)cancelTitle
                         grantTitle:(NSString *)grantTitle
                  completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)healthAuthorized;
- (void)authorizeHealth:(AuthorizationBlock) completionHandler;
- (void)authorizeHealthWithTitle:(NSString *)messageTitle
                         message:(NSString *)message
                     cancelTitle:(NSString *)cancelTitle
                      grantTitle:(NSString *)grantTitle
               completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)locationsAuthorized;
- (void)authorizeLocations:(AuthorizationBlock)completionHandler;
- (void)authorizeLocationsWithTitle:(NSString *)messageTitle
                            message:(NSString *)message
                        cancelTitle:(NSString *)cancelTitle
                         grantTitle:(NSString *)grantTitle
                  completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)microphoneAuthorized;
- (void)authorizeMicrophone:(AuthorizationBlock) completionHandler;
- (void)authorizeMicrophoneWithTitle:(NSString *)messageTitle
                             message:(NSString *)message
                         cancelTitle:(NSString *)cancelTitle
                          grantTitle:(NSString *)grantTitle
                   completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)twitterAuthorized;
- (void)authorizeTwitter:(AuthorizationBlock)completionHandler;
- (void)authorizeTwitterWithTitle:(NSString *)messageTitle
                          message:(NSString *)message
                      cancelTitle:(NSString *)cancelTitle
                       grantTitle:(NSString *)grantTitle
                completionHandler:(AuthorizationBlock)completionHandler;

- (BOOL)facebookAuthorized;
- (void)authorizeFacebook:(AuthorizationBlock)completionHandler;
- (void)authorizeFacebookWithTitle:(NSString *)messageTitle
                           message:(NSString *)message
                       cancelTitle:(NSString *)cancelTitle
                        grantTitle:(NSString *)grantTitle
                 completionHandler:(AuthorizationBlock)completionHandler;


- (BOOL)notificationsAuthorized;
- (void)authorizeNotifications:
        (NotificationAuthorizationBlock)completionHandler;
- (void)authorizeNotificationsWithTitle:(NSString *)messageTitle
                                message:(NSString *)message
                            cancelTitle:(NSString *)cancelTitle
                             grantTitle:(NSString *)grantTitle
                      completionHandler:(NotificationAuthorizationBlock)completionHandler;
- (void)unauthorizeNotifications;
- (void)notificationResult:(NSData *)deviceToken error:(NSError *)error;
- (NSString *)deviceID;

```

## Author

- [Joe Laws]

## Projects

Here is a list of iPhone apps utilizing this library (let me know if you want your app added):

- [Faysee] - [Faysee Homepage]

## License

JLAddressBook is available under the MIT license. See the LICENSE file for more info.

[Joe Laws]:https://angel.co/joe-laws
[Faysee]:https://itunes.apple.com/us/app/seer-reminders/id721450216?ls=1&mt=8
[Faysee Homepage]:http://faysee.com

