# Stream Markers Documentation

## Get Stream Markers

This is an example of how to get stream markers. You can request the stream markers of
a VOD or a livestream of an user if it is recorded as VOD as well. Here we are
requesting the first two stream markers of a VOD. The authenticated user requires the
`user:read:broadcast` scope to be able to request stream markers of this user.

```go
client, err := helix.NewClient(&helix.Options{
    ClientID:        "your-client-id",
    UserAccessToken: "your-user-access-token",
})

if err != nil {
    // handle error
}

resp, err := client.GetStreamMarkers(&helix.StreamMarkersParams{
    First: 2,
    VideoID: "123",
})
if err != nil {
    // handle error
}

fmt.Printf("%+v\n", resp)
```