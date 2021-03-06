# V6: Environmental Interaction Requirements

## Control Objective

The controls in this group ensure that the app uses platform APIs and standard components in a secure manner. Additionally, the controls cover communication between apps (IPC).

## Security Verification Requirements

| # | Description | L1 | L2 |
| --- | --- | --- | --- |
| **6.1** | The app only requests the minimum set of permissions necessary. | ✓ | ✓ |
| **6.2** | All inputs from external sources and the user are validated and if necessary sanitized. This includes data received via the UI, IPC mechanisms such as intents, custom URLs, and network sources.| ✓ | ✓ |
| **6.3** | The app does not export sensitive functionality via custom URL schemes, unless these mechanisms are properly protected. | ✓ | ✓ |
| **6.4** | The app does not export sensitive functionality through IPC facilities, unless these mechanisms are properly protected. | ✓ | ✓ |
| **6.5** | JavaScript is disabled in WebViews unless explicitly required. | ✓ | ✓ |
| **6.6** | WebViews are configured to allow only the minimum set of protocol handlers required (ideally, only https is supported). Potentially dangerous handlers, such as file, tel and app-id, are disabled. | ✓ | ✓ |
| **6.7** | The app does not load user-supplied local resources into WebViews. | ✓ | ✓ |
| **6.8** | If Java objects are exposed in a WebView, verify that the WebView only renders JavaScript contained within the app package. | ✓ | ✓ |
| **6.9** | Object serialization, if any, is implemented using safe serialization APIs. | ✓ | ✓ |
| **6.10** | The app detects whether it is being executed on a rooted or jailbroken device. Depending on the business requirement, users are warned, or the app is terminated if the device is rooted or jailbroken. |  | ✓ |

## References

The OWASP Mobile Security Testing Guide provides detailed instructions for verifying the requirements listed in this section, as well as best practices by mobile operating system:

(...TODO... link this to v1.0 instead of master once tagged).

- Android - https://github.com/OWASP/owasp-mstg/blob/master/Document/Testcases/0x01e_OMTG-ENV_Android.md
- iOS - https://github.com/OWASP/owasp-mstg/blob/master/Document/Testcases/0x02e_OMTG-ENV_iOS.md

For more information, see also:

- OWASP Mobile Top 10: M1 - Improper Platform Usage
- CWE: https://cwe.mitre.org/data/definitions/20.html
- CWE: https://cwe.mitre.org/data/definitions/749.html
