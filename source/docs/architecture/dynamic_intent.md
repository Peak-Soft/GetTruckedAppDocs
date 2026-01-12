# Dynamic Intent Architecture

The `DynamicIntent` class is a crucial architectural component in the SmartCargo application. It solves the problem of having two distinct user flows (Mover vs. Lorry) within a single application codebase.

## Purpose

To dynamically resolve the destination `Activity` class based on the currently logged-in user's account type (`"user"` for Movers or `"company"` for Lorry drivers). This allows the code to use a generic target class request, which is then intercepted and redirected to the package-specific implementation.

## Implementation Details

**Class Location:** `com.cscodetech.common.utils.DynamicIntent`

### Logic Flow

1.  **Account Type Check:** The class retrieves the `UserLogin` details from `SessionManager`.
2.  **Package Selection:**
    - If account type is `company`, the target package is set to `com.cscodetech.moverslorry`.
    - If account type is `user`, the target package is set to `com.cscodetech.movers`.
3.  **Class Name Construction:**
    - It takes the base name of the `targetClass` passed to the constructor.
    - It strips existing package prefixes (`com.cscodetech.movers` or `com.cscodetech.moverslorry`) to get the raw Activity name.
    - It prepends the correct package prefix determined in step 2.
4.  **Reflection:** It uses `Class.forName(activityName)` to load the correct class at runtime.

### Code Example

```java
public class DynamicIntent extends Intent {
    private static final String MOVER_PACKAGE = "com.cscodetech.moverslorry";
    private static final String CLIENT_PACKAGE = "com.cscodetech.movers";

    private static Class<?> getActivityClass(Class targetClass, Context context) {
        // ... Session logic ...
        
        String activityName = targetClass.getName()
            .replace(CLIENT_PACKAGE + ".", "")
            .replace(MOVER_PACKAGE + ".", "");

        if ("company".equals(accountType)) {
            activityName = MOVER_PACKAGE + "." + activityName;
        } else {
            activityName = CLIENT_PACKAGE + "." + activityName;
        }

        return Class.forName(activityName);
    }
}
```

## Usage

When starting an activity that exists in both modules (e.g., `HomeActivity`, `ProfileFragment` host), use `DynamicIntent` instead of a standard `Intent`.

```java
// Instead of:
// Intent intent = new Intent(context, com.cscodetech.movers.HomeActivity.class);

// Use:
Intent intent = new DynamicIntent(context, HomeActivity.class);
startActivity(intent);
```

This ensures that a Company user is sent to `com.cscodetech.moverslorry.HomeActivity` and a normal User is sent to `com.cscodetech.movers.HomeActivity`.
