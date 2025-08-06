# Mobile Compass App

A simple, responsive HTML compass app that uses device orientation sensors to show real-time compass direction on mobile devices.

## Features

- **Real-time compass needle** that rotates based on device orientation
- **Haptic feedback** - device vibrates when pointing north (within 10°)
- **Visual north indicator** - compass glows red and pulses when north is detected
- **Responsive design** that works on all screen sizes
- **Permission handling** for iOS 13+ devices that require explicit permission
- **Multiple sensor support** including DeviceOrientationEvent and Geolocation API
- **Visual compass face** with cardinal directions and degree markings
- **Static crosshair** in the center to highlight compass rotation
- **Bearing display** showing exact degree and cardinal direction
- **Error handling** with user-friendly messages
- **Optimized performance** with 60fps updates and hardware acceleration
- **Multiple performance modes** (Ultra Responsive, Balanced, Smooth)
- **Advanced smoothing algorithms** to reduce sensor noise while maintaining responsiveness
- **Debug panel** with real-time API status and event logging for troubleshooting

## Browser Compatibility

- **iOS Safari**: Supports `webkitCompassHeading` and requires permission on iOS 13+
- **Android Chrome**: Uses `DeviceOrientationEvent.alpha` for compass heading
- **Other modern browsers**: Falls back to available orientation APIs

## Usage

1. Open `index.html` in a mobile browser
2. If prompted, grant permission for device orientation access
3. Hold your device flat (parallel to the ground) for best accuracy
4. The red needle always points to magnetic North (upward on screen)
5. The compass face rotates as you turn your device, keeping the needle pointing north
6. A small crosshair in the center helps visualize the compass rotation
7. When your device points north (within 10°), it will vibrate and the compass will glow red
8. The bearing display shows your current heading in degrees and cardinal direction
9. Click "Show Debug Info" to view API support status and real-time event logs
10. Use the performance mode buttons to adjust responsiveness vs smoothness

## Technical Details

### APIs Used

- **DeviceOrientationEvent**: Primary source for device orientation
- **DeviceOrientationAbsoluteEvent**: Preferred for absolute orientation
- **Geolocation API**: Fallback for devices with GPS compass
- **Vibration API**: Provides haptic feedback when north is detected
- **Permission API**: For iOS 13+ permission requests

### Sensor Data Processing

- Handles different browser implementations (`webkitCompassHeading` vs `alpha`)
- Normalizes heading values to 0-360 degree range
- Provides smooth transitions with CSS animations and hardware acceleration
- Accounts for different coordinate systems across platforms
- Uses requestAnimationFrame for 60fps updates
- Implements exponential smoothing to reduce sensor noise
- Offers multiple performance modes for different use cases

### Security Features

- HTTPS required for device orientation access on most browsers
- Permission-based access following modern web standards
- Graceful degradation when sensors are unavailable

## Local Development

Simply open `index.html` in a web browser. For testing device orientation:

1. Use browser developer tools device simulation
2. Test on actual mobile devices for real sensor data
3. Ensure HTTPS when testing on remote devices

## Debug Features

The app includes a comprehensive debug panel to help troubleshoot issues:

- **API Support Check**: Shows which APIs are available on your device
- **Real-time Status**: Displays current heading, vibration history, and device state
- **Event Logging**: Logs all orientation events, permission requests, and errors
- **Platform Detection**: Identifies iOS vs Android and shows user agent info
- **Performance Controls**: Switch between Ultra Responsive, Balanced, and Smooth modes
- **Performance Metrics**: Shows update frequency, smoothing factor, and performance mode

To access debug info, click the "Show Debug Info" button at the bottom of the app.

### Performance Modes

- **Ultra Responsive**: ~120fps updates, minimal smoothing, instant needle movement
- **Balanced**: ~60fps updates, moderate smoothing, slight transition smoothing
- **Smooth**: ~30fps updates, heavy smoothing, smooth transitions (default)

## Troubleshooting

- **No orientation data**: Ensure device has orientation sensors and permissions are granted
- **Inaccurate readings**: Keep device flat and away from magnetic interference
- **Permission denied**: Check browser settings and reload the page
- **iOS issues**: Make sure to tap the permission button when prompted
- **No vibration**: Ensure device supports vibration API and is not in silent mode
- **Vibration too frequent**: There's a 2-second cooldown between vibrations when pointing north
- **iOS vibration issues**: Check debug panel - iOS may not support vibration in web apps or when device is in silent mode
- **Sluggish response**: Try "Ultra Responsive" mode in debug panel for faster updates
- **Jittery needle**: Use "Smooth" mode for more stable movement with sensor noise

## License

This project is open source and available under the terms specified in the LICENSE file.