
# LinkFivePurchases iOS SDK

This SDK allows you to conveniently manage your subscriptions.

Installation
------------

### Swift Package Manager

To integrate using Apple's Swift package manager, add the following as a dependency to your `Package.swift`:

```swift
.package(url: "https://github.com/LinkFive/ios-purchases-sdk.git", .upToNextMajor(from: "1.0.0"))
```

Then, specify `"LinkFivePurchases"` as a dependency of the Target in which you wish to use LinkFivePurchases.

Lastly, run the following command:
```swift
swift package update
```

Usage
-------------

### Initialize the SDK

You need to initialize the SDK with your API KEY from the dashboard.

```swift
LinkFivePurchases.shared.launch(with: "YOUR_API_KEY")
```

### Fetch all available subscriptions

`fetchSubscriptions` returns a result with a list of `SKProducts` which have been made available through the LinkFive dashboard.

```swift
LinkFivePurchases.shared.fetchSubscriptions { result in
    // TODO: Process the result
}
```

### Get current receipt info

To check if there is a current receipt and whether it's valid, use `fetchReceiptInfo`. It fetches the receipt info mostly from cache, but you can also force it to fetch the receipt info from the server.

```swift
LinkFivePurchases.shared.fetchReceiptInfo { result in
    // TODO: Process the result
}
```

### Purchase a subscription

To purchase a subscription, use `purchase` with a `SKProduct`. It returns whether the purchase has been successful. 
```swift
LinkFivePurchases.shared.purchase(product: product) { result in
    // TODO: Process the result
}
```

### Restore a subscription

To restore a subscription, use `restore`. It returns whether the restore has been successful. 
```swift
LinkFivePurchases.shared.restore { result in
    // TODO: Process the result
}
```

## License

LinkFivePurchases is released under an MIT license. See [LICENSE](https://github.com/LinkFive/ios-purchases-sdk/blob/main/LICENSE) for more information.
