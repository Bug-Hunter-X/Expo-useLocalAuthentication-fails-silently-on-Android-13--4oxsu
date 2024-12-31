# Expo useLocalAuthentication Android 13+ Issue

This repository demonstrates a bug in Expo's `useLocalAuthentication` hook on Android 13 and higher. The `authenticateAsync` function intermittently fails to prompt the user for biometric authentication, returning an error without any user interaction. This issue is inconsistent and doesn't always reproduce.

## Bug Description

The `useLocalAuthentication` hook, when used with Android 13 or later, sometimes fails to display the biometric authentication prompt.  The `authenticateAsync` function returns an error, often an empty object or an error with code 'canceled', without any indication of why authentication failed.  This behavior is different on older Android versions where it functions correctly.

## Steps to Reproduce

1. Clone this repository.
2. Run the project on an Android emulator or device running Android 13 or higher.
3. Observe that the authentication prompt sometimes fails to appear, leading to an error in the console.

## Potential Workarounds (Investigate)

While a definitive solution isn't included here, potential areas of investigation include:
* **Checking for specific Android permissions beyond those typically handled by Expo:** Ensure that all necessary permissions are properly requested and granted.
* **Inspecting the Android system logs:** Search for relevant error messages related to biometric authentication to pinpoint the root cause.
* **Testing with different biometric authentication methods:**  Experiment with different authentication methods (fingerprint, face unlock) to determine if the issue is specific to one method.
* **Exploring alternative authentication libraries:** Consider using a native module or different authentication library to bypass the potential Expo issue.

## Contributions

Contributions and solutions are welcome.  Please open an issue or submit a pull request with your findings.