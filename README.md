# Mobile Compass App

A simple, responsive HTML compass app that uses device orientation sensors to show real-time compass direction on mobile devices.

## Features

- **Real-time compass needle** that rotates based on device orientation
- **Responsive design** that works on all screen sizes
- **Permission handling** for iOS 13+ devices that require explicit permission
- **Multiple sensor support** including DeviceOrientationEvent and Geolocation API
- **Visual compass face** with cardinal directions and degree markings
- **Bearing display** showing exact degree and cardinal direction
- **Error handling** with user-friendly messages
- **Smooth animations** for needle movement

## Browser Compatibility

- **iOS Safari**: Supports `webkitCompassHeading` and requires permission on iOS 13+
- **Android Chrome**: Uses `DeviceOrientationEvent.alpha` for compass heading
- **Other modern browsers**: Falls back to available orientation APIs

## Usage

1. Open `index.html` in a mobile browser
2. If prompted, grant permission for device orientation access
3. Hold your device flat (parallel to the ground) for best accuracy
4. The red needle points to magnetic North
5. The bearing display shows your current heading in degrees and cardinal direction

## Technical Details

### APIs Used

- **DeviceOrientationEvent**: Primary source for device orientation
- **DeviceOrientationAbsoluteEvent**: Preferred for absolute orientation
- **Geolocation API**: Fallback for devices with GPS compass
- **Permission API**: For iOS 13+ permission requests

### Sensor Data Processing

- Handles different browser implementations (`webkitCompassHeading` vs `alpha`)
- Normalizes heading values to 0-360 degree range
- Provides smooth transitions with CSS animations
- Accounts for different coordinate systems across platforms

### Security Features

- HTTPS required for device orientation access on most browsers
- Permission-based access following modern web standards
- Graceful degradation when sensors are unavailable

## Local Development

Simply open `index.html` in a web browser. For testing device orientation:

1. Use browser developer tools device simulation
2. Test on actual mobile devices for real sensor data
3. Ensure HTTPS when testing on remote devices

## Troubleshooting

- **No orientation data**: Ensure device has orientation sensors and permissions are granted
- **Inaccurate readings**: Keep device flat and away from magnetic interference
- **Permission denied**: Check browser settings and reload the page
- **iOS issues**: Make sure to tap the permission button when prompted

## License

This project is open source and available under the terms specified in the LICENSE file.