# Edens Toast Notifications

A simple toast notification API for VRChat mods built using MelonLoader.  
I had multiple mods needing toast notifications, leading me to want to have it in once place.
So I made this for myself.

I know a lot of people already use their own notification stuff but I figured I’d share this in case it’s useful to anyone else.
I won't be providing support for it though further than this Readme.

---

## 🔧 Features

- ✅ Queue-based toast system
- ✅ Immediate (forced) toasts
- ✅ Delayed queue or forced toasts
- ✅ Optional max queue control
---


## 📦 Installation

Add this mod to your `Mods` folder like any other MelonLoader-based VRChat mod.

If you're a mod developer and want to use the API:

```csharp
using ToastNotificationAPI;
```

---

## 💡 Usage

### 1. Queue a Toast

Shows a toast after any currently showing ones finish.

```csharp
ToastNotification.QueueToast("Hello World!", "This is a queued toast notification.", null, 3f);
```

---

### 2. Force a Toast Immediately

Skips the queue and shows the toast right away.

```csharp
ToastNotification.ForceToast("Important!", "This toast shows immediately.", null, 4f);
```

---

### 3. Delay-Queued Toast

Adds a toast to the queue after a delay (in seconds).

```csharp
ToastNotification.DelayQueueToast(5f, "Delayed Queue", "This toast was queued after a delay.", null, 3f);
```

---

### 4. Delay-Forced Toast

Skips the queue, but only after a delay.

```csharp
ToastNotification.DelayForceToast(3f, "Delayed Force", "This toast shows immediately after a delay.", null, 4f);
```

---

### 5. Conditionally Queue a Toast

Only adds to the queue if the queue count is below your specified limit.  
Returns `true` if it was added, `false` if skipped.

```csharp
bool success = ToastNotification.ConditionalQueueToast(3, "Queued Conditionally", "Won't queue if too many toasts are pending.");
```

---

## 📚 Other Utilities

```csharp
ToastNotification.ClearQueue();       // Clears the current queue
int count = ToastNotification.QueueCount();  // Get number of pending toasts
```

---

## 🧠 Why?

This isn't meant to be groundbreaking.
Just a clean, modular way to handle toast notifications consistently across multiple of my own mods.


## 🙋‍♂️ Author

Made by [EdenFails](https://github.com/EdenFails)  
If you find this useful, cool. If not then eh cos I made it for me anyways. 😛
