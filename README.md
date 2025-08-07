# _videosdk_idb_

# Mục Lục

- [Hướng dẫn tích hợp chức năng Sessions](#hướng-dẫn-tích-hợp-chức-năng-sessions)
  - [1. Join session](#1-join-session)
  - [2. End session](#2-end-session)
- [Hướng dẫn tích hợp chức năng Video](#hướng-dẫn-tích-hợp-chức-năng-video)
  - [1. Chi tiết phân tích](#1-chi-tiết-phân-tích)
  - [2. Tách Riêng Toàn Màn Hình và Danh Sách Cuộn Ngang](#2-tách-riêng-toàn-màn-hình-và-danh-sách-cuộn-ngang)
    - [2.1. Định Nghĩa Lớp VideoView](#21-định-nghĩa-lớp-videoview)
    - [2.2. Sử Dụng VideoView trong Giao Diện Ứng Dụng](#22-sử-dụng-videoview-trong-giao-diện-ứng-dụng)
      - [2.2.2. Giải Thích Mã Nguồn](#222-giải-thích-mã-nguồn)
        - [VideoView cho Toàn Màn Hình](#videoview-cho-toàn-màn-hình)
        - [VideoView cho Danh Sách Cuộn Ngang](#videoview-cho-danh-sách-cuộn-ngang)
  - [3. Truyền Tham Số Tạo Cho VideoView](#3-truyền-tham-số-tạo-cho-videoview)
- [Hướng Dẫn Quản Lý Âm Thanh, camera, micro, đèn flash trong Ứng Dụng Sử Dụng Video SDK](#hướng-dẫn-quản-lý-âm-thanh-camera-micro-đèn-flash-trong-ứng-dụng-sử-dụng-video-sdk)

  - [1. Quản lý âm thanh](#1-quản-lý-âm-thanh)
    - [1. Kiểm Tra Trạng Thái Kết Nối Âm Thanh](#1-kiểm-tra-trạng-thái-kết-nối-âm-thanh)
      - [1.1. Kiểm Tra Người Dùng Có Bị Tắt Tiếng](#11-kiểm-tra-người-dùng-có-bị-tắt-tiếng)
      - [1.2. Kiểm Tra Người Dùng Có Đang Nói Chuyện](#12-kiểm-tra-người-dùng-có-đang-nói-chuyện)
      - [1.3. Kiểm Tra Người Dùng Có Kết Nối Âm Thanh](#13-kiểm-tra-người-dùng-có-kết-nối-âm-thanh)
    - [2. Kết Nối Người Dùng với Âm Thanh](#2-kết-nối-người-dùng-với-âm-thanh)
      - [2.1. Kết Nối Âm Thanh](#21-kết-nối-âm-thanh)
      - [2.2. Tắt/Mở Âm Thanh Người Dùng](#22-tắtmở-âm-thanh-người-dùng)
        - [2.2.1. Tắt Âm Thanh Người Dùng](#221-tắt-âm-thanh-người-dùng)
        - [2.2.2. Mở Âm Thanh Người Dùng](#222-mở-âm-thanh-người-dùng)
    - [3. Ngắt Kết Nối Âm Thanh](#3-ngắt-kết-nối-âm-thanh)
    - [4. Tùy Chọn Âm Thanh Nâng Cao](#4-tùy-chọn-âm-thanh-nâng-cao)
      - [4.1. Bật Âm Thanh Gốc](#41-bật-âm-thanh-gốc)
      - [4.2. Tắt Âm Thanh Gốc](#42-tắt-âm-thanh-gốc)
  - [2. Quản lý camera](#2-quản-lý-camera)
    - [2.1. Bật tắt (On/Off) camera (startVideo)](#21-bật-tắt-onoff-camera-startvideo)
    - [2.2. Switch camera (Hoán đổi ống kính camera)](#22-switch-camera-hoán-đổi-ống-kính-camera)
    - [2.3. Bật tắt Mirror video (lật video)](#23-bật-tắt-mirror-video-lật-video)
  - [3. Quản lý microphone](#3-quản-lý-microphone)
  - [4. Quản lý đèn flashlight](#4-quản-lý-đèn-flashlight)
    - [Bật/Tắt flashlight trên iOS](#bậttắt-flashlight-trên-ios)
    - [Lấy giá trị flashlight trên iOS](#lấy-giá-trị-flashlight-trên-ios)
    - [Bật/tắt flashlight trên Android](#bậttắt-flashlight-trên-android)
    - [Lấy giá trị flashlight trên Android](#lấy-giá-trị-flashlight-trên-android)
    - [Quản lý pip mode in android (do android phải setup riêng , IOS đã được hỗ trợ sẵn)](#5-quản-lý-pip-mode-in-android-do-android-phải-setup-riêng--ios-đã-được-hỗ-trợ-sẵn)

- [5. Hướng Dẫn Sử Dụng Tính Năng Chat trong Ứng Dụng Sử dụng Video SDK](#5-hướng-dẫn-sử-dụng-tính-năng-chat-trong-ứng-dụng-sử-dụng-video-sdk)
  - [1. Các Thành Phần Chính của Video SDK cho Chat](#1-các-thành-phần-chính-của-video-sdk-cho-chat)
  - [2. Gửi tin nhắn](#2-gửi-tin-nhắn)
    - [2.1. Tin Nhắn Riêng Tư](#21-tin-nhắn-riêng-tư)
    - [2.2. Tin Nhắn Công Khai](#22-tin-nhắn-công-khai)
  - [3. Nhận Tin Nhắn](#3-nhận-tin-nhắn)
  - [4. Định Nghĩa Các Thuộc Tính của Tin Nhắn](#4-định-nghĩa-các-thuộc-tính-của-tin-nhắn)
- [6. Hướng Dẫn Thiết Lập và Sử Dụng Command Channel trong Ứng Dụng Sử dụng Video SDK](#6-hướng-dẫn-thiết-lập-và-sử-dụng-command-channel-trong-ứng-dụng-sử-dụng-video-sdk)
  - [1. Các Thành Phần Chính của Command Channel](#1-các-thành-phần-chính-của-command-channel)
  - [2. Các Bước Thiết Lập Command Channel](#2-các-bước-thiết-lập-command-channel)
    - [2.1. Lấy Instance của Command Channel](#21-lấy-instance-của-command-channel)
    - [2.2. Chờ Command Channel Trở Thành Hoạt Động](#22-chờ-command-channel-trở-thành-hoạt-động)
    - [2.3. Gửi Lệnh](#23-gửi-lệnh)
      - [2.3.1. Gửi Lệnh đến Người Dùng Cụ Thể](#231-gửi-lệnh-đến-người-dùng-cụ-thể)
      - [2.3.2. Gửi Lệnh đến Toàn Bộ Phiên gọi](#232-gửi-lệnh-đến-toàn-bộ-phiên-gọi)
    - [2.4. Nhận Lệnh](#24-nhận-lệnh)
- [7. Hướng dẫn setup chức năng share màn hình cho dự án](#7-hướng-dẫn-setup-chức-năng-share-màn-hình-cho-dự-án)
  - [iOS platform](#ios-platform)
    - [1. Giới Thiệu](#1-giới-thiệu)
    - [2. Các Bước Triển Khai Broadcast Màn Hình Thiết Bị](#2-các-bước-triển-khai-broadcast-màn-hình-thiết-bị)
      - [2.1. Yêu Cầu Trước Khi Bắt Đầu](#21-yêu-cầu-trước-khi-bắt-đầu)
      - [2.2. Tạo Một Target Mới](#22-tạo-một-target-mới)
    - [Cấu Hình Podfile cho Dự Án iOS](#cấu-hình-podfile-cho-dự-án-ios)
    - [Thêm Đường Dẫn Vào Dự Án Xcode](#thêm-đường-dẫn-vào-dự-án-xcode)
    - [Add các permission này vào file info.plist thuộc Broadcast extension](#add-các-permission-này-vào-file-infoplist-thuộc-broadcast-extension)
    - [Tích hợp ZoomVideoSDKScreenShare với thư viện C++](#tích-hợp-zoomvideosdkscreenshare-với-thư-viện-c)
    - [Tích hợp AppGroupId vào dự án](#tích-hợp-appgroupid-vào-dự-án)
    - [Cập Nhật File SampleHandler.swift cho Extension Broadcast Upload](#cập-nhật-file-samplehandlerswift-cho-extension-broadcast-upload)
      - [Thay thế nội dung của file SampleHandler.swift trong extension Broadcast upload bằng đoạn mã sau:](#thay-thế-nội-dung-của-file-samplehandlerswift-trong-extension-broadcast-upload-bằng-đoạn-mã-sau)
  - [Android platform](#android-platform)
  - [Flutter](#flutter)
    - [1. Lấy Instance của VideoSDKShareHelper](#1-lấy-instance-của-videosdksharehelper)
    - [2. Kiểm Tra Trạng Thái Chia Sẻ](#2-kiểm-tra-trạng-thái-chia-sẻ)
    - [3. Gửi Lệnh Chia Sẻ Màn Hình](#3-gửi-lệnh-chia-sẻ-màn-hình)
    - [4. Thêm Callbacks để Theo Dõi Trạng Thái Chia Sẻ](#4-thêm-callbacks-để-theo-dõi-trạng-thái-chia-sẻ)
      - [4.1. Tạo và Đăng Ký Event Listener](#41-tạo-và-đăng-ký-event-listener)

## Hướng dẫn tích hợp chức năng Sessions

### Cài đặt

#### Nếu sử dụng link git hoặc các nền tảng source management khác thì sẽ cấu hình như sau:

- Trong file pubspec.yaml, thêm đoạn code này nếu sử dụng bitbucket

```yaml
videosdk_idb:
  git:
    url: git@bitbucket.org:your_username/your_repository.git
    ref: master # hoặc branch/tag cụ thể
```

hoặc nếu là github thì thêm

```yaml
videosdk_idb:
  git:
    url: git@github.com:your_username/your_repository.git
    ref: master # hoặc branch/tag cụ thể
```

#### Nếu sử dụng local source

- Bước 1: Tạo thư mục tên "modules" cùng cấp với thư mục Lib
- Bước 2: copy thư mục source thư viện vào thư mục modules
- Bước 3: Thêm đoạn code này vào file pubspec.yaml

```yaml
videosdk_idb:
  path: "./modules/videosdk_idb"
```

### Cấu hình

- Khởi tạo sdk khi bắt đầu khởi động app

```dart
 var videoSdk = VideoSdk();
    InitConfigVideoSdk initConfig = InitConfigVideoSdk(
      domain: "",
      enableLog: true,
      appGroupId: "enter appgroudId here",
      screeShareBundleId: "enter screen share bundle Id here",
    );
    videoSdk.initSdk(initConfig);
```

### 1. Join session

- Để có thể join a session, sử dụng model JoinSessionConfigVideoSdk trong VideoIdb_Sdk instance:

```dart
Future<void>.microtask(() async {
        try {
          String sessionId = await videoSdk.session.getSessionID() as String;
          Map<String, bool> SDKaudioOptions = {
            "connect": true,
            "mute": true,
            "autoAdjustSpeakerVolume": false
          };
          Map<String, bool> SDKvideoOptions = {
            "localVideoOn": true,
          };
          JoinSessionConfigVideoSdk joinSession = JoinSessionConfigVideoSdk(
            sessionName: args.sessionName,
            sessionPassword: args.sessionPwd,
            token: args.videoJWT,
            userName: args.displayName,
            audioOptions: SDKaudioOptions,
            videoOptions: SDKvideoOptions,
            sessionIdleTimeoutMins: int.parse(args.sessionIdleTimeoutMins),
          );
          await videoSdk
              .joinSession(joinSession)
              .then((value) => {print("value $value")});


        } catch (e) {

        }
      });
```

### 2. End session

```dart
 void onLeaveSession() async {
      var mySelf = await videoSdk.session.getMySelf();
      bool isHost = await mySelf!.getIsHost();

      if (isHost) {
        await videoSdk.leaveSession(true);
      } else {
        await videoSdk.leaveSession(false);
      }
    }
```

## Hướng dẫn tích hợp chức năng Video

### 1. Chi tiết phân tích:

- Sử dụng Widget tương ứng cho từng nền tảng:

- AndroidView: Được sử dụng để hiển thị video trên nền tảng Android.

- UiKitView: Được sử dụng để hiển thị video trên nền tảng iOS.
  Định nghĩa lớp View: Đoạn mã định nghĩa một lớp View để render (hiển thị) video view phù hợp với từng nền tảng. Điều này đảm bảo rằng ứng dụng có thể hoạt động một cách mượt mà trên cả Android và iOS.

```dart
switch (defaultTargetPlatform) {
  case TargetPlatform.android:
    return AndroidView(
      viewType: 'the name of view type',
      layoutDirection: TextDirection.ltr,
      creationParams: creationParams,
      creationParamsCodec: const StandardMessageCodec(),
    );
  case TargetPlatform.iOS:
    return UiKitView(
      viewType: 'the name of view type',
      layoutDirection: TextDirection.ltr,
      creationParams: creationParams,
      creationParamsCodec: const StandardMessageCodec(),
    );
  default:
    throw UnsupportedError("Unsupported platform");
}
```

### 2. Tách Riêng Toàn Màn Hình và Danh Sách Cuộn Ngang

- Để thực hiện chức năng này, chúng ta sẽ định nghĩa một lớp VideoView riêng biệt để render video dựa trên việc nó có ở chế độ toàn màn hình hay không.
  2.1. Định Nghĩa Lớp VideoView
  Đầu tiên, hãy tạo một lớp VideoView mở rộng từ HookWidget. Lớp này sẽ nhận các tham số để xác định cách hiển thị video.

```dart
import 'dart:async';
import 'dart:developer';

import 'package:flutter/material.dart';
import 'package:flutter_hooks/flutter_hooks.dart';
import 'package:videosdk_idb/native/videosdk.dart';
import 'package:videosdk_idb/videosdk_idb_view.dart' as VideoIdbView;

class VideoView extends VideoIdbView.VideoSdkView  {
  const VideoView({
    super.key,
    required super.user,
    required super.sharing,
    required super.preview,
    required super.focused,
    required super.hasMultiCamera,
    required super.isPiPView,
    required super.multiCameraIndex,
    required super.videoAspect,
    required super.fullScreen,
    required super.resolution,
  });

  const VideoView({
    Key? key,
    required this.user,
    required this.sharing,
    required this.preview,
    required this.focused,
    required this.hasMultiCamera,
    required this.multiCameraIndex,
    this.videoAspect,
    required this.fullScreen,
  }) : super(key: key);

  @override
  Widget build(BuildContext context) {
    // Implement rendering logic based on fullScreen flag
    // Ví dụ:
    if (fullScreen) {
      return _buildFullScreenView();
    } else {
      return _buildHorizontalListView();
    }
  }

  Widget _buildFullScreenView() {
    // Implement full screen view rendering
    return Container(
      // Thêm widget hiển thị video toàn màn hình
      color: Colors.black,
      child: Center(
        child: Text(
          user?.name ?? 'User',
          style: TextStyle(color: Colors.white),
        ),
      ),
    );
  }

  Widget _buildHorizontalListView() {
    // Implement horizontal list view rendering
    return Container(
      width: 100,
      height: 100,
      color: Colors.grey,
      child: Center(
        child: Text(
          user?.name ?? 'User',
          style: TextStyle(color: Colors.white),
        ),
      ),
    );
  }
}
```

#### 2.2. Sử Dụng VideoView trong Giao Diện Ứng Dụng

Trong tệp lib/call-screen.dart, chúng ta sẽ sử dụng VideoView trong hai khối mã riêng biệt: một cho chế độ toàn màn hình và một cho danh sách cuộn ngang.

```dart
import 'package:flutter/material.dart';
import 'VideoView.dart'; // Import lớp VideoView

class CallScreen extends StatelessWidget {
  final VideoSdkUser? fullScreenUser;
  final bool sharing;
  final VideoSdkUser? sharingUser;

  CallScreen({
    this.fullScreenUser,
    required this.sharing,
    this.sharingUser,
  });

  @override
  Widget build(BuildContext context) {
    double opacityLevel = 1.0; // Ví dụ về mức độ mờ

    return Scaffold(
      appBar: AppBar(
        title: Text('Call Screen'),
      ),
      body: Stack(
        children: [
          // Toàn màn hình visualization
          AnimatedOpacity(
            opacity: opacityLevel,
            duration: Duration(seconds: 3),
            child: VideoView(
              user: fullScreenUser,
              hasMultiCamera: false,
              sharing: sharingUser?.userId == fullScreenUser?.userId,
              preview: false,
              focused: false,
              multiCameraIndex: "0",
              videoAspect: "Original",
              fullScreen: true,
            ),
          ),
          // Danh sách cuộn ngang ở dưới cùng
          Positioned(
            bottom: 0,
            left: 0,
            right: 0,
            child: _buildHorizontalListView(),
          ),
        ],
      ),
    );
  }

  Widget _buildHorizontalListView() {
    List<VideoSdkUser> users = []; // Danh sách người dùng tham gia

    return Container(
      height: 110,
      margin: const EdgeInsets.symmetric(horizontal: 20),
      alignment: Alignment.center,
      child: ListView.separated(
        scrollDirection: Axis.horizontal,
        itemCount: users.length,
        itemBuilder: (BuildContext context, int index) {
          VideoSdkUser user = users[index];
          return InkWell(
            onTap: () {
              // Xử lý khi người dùng nhấn vào video của người khác
              // Ví dụ: Đặt người dùng này vào chế độ toàn màn hình
            },
            child: Center(
              child: VideoView(
                user: user,
                hasMultiCamera: false,
                sharing: sharingUser?.userId == user.userId,
                preview: false,
                focused: false,
                multiCameraIndex: "0",
                videoAspect: "Original",
                fullScreen: false,
              ),
            ),
          );
        },
        separatorBuilder: (BuildContext context, int index) => Divider(),
      ),
    );
  }
}
```

##### 2.2.2. Giải Thích Mã Nguồn

###### VideoView cho Toàn Màn Hình:

- user: Đối tượng người dùng được hiển thị ở chế độ toàn màn hình.
- fullScreen: Đặt giá trị true để hiển thị chế độ toàn màn hình.
- Các tham số khác như sharing, preview, focused được thiết lập dựa trên trạng thái của người dùng.

###### VideoView cho Danh Sách Cuộn Ngang:

- user: Đối tượng người dùng trong danh sách cuộn ngang.
- fullScreen: Đặt giá trị false để hiển thị trong danh sách cuộn ngang.
- Khi người dùng nhấn vào một video trong danh sách, bạn có thể cập nhật người dùng đó thành người dùng chính để hiển thị ở chế độ toàn màn hình.

### 3. Truyền Tham Số Tạo Cho VideoView

Khi tạo các đối tượng VideoView, chúng ta truyền các tham số sau:

- **_user_**: Đối tượng VideoSdkUser được khởi tạo thông qua event listener khi người dùng tạo, tham gia hoặc rời khỏi phiên họp.
- **_sharing_**: Boolean được đặt true nếu người dùng hiện tại đang chia sẻ màn hình.
- **_preview_**: Boolean được đặt true nếu video view là để xem trước.
- **_hasMultiCamera_**: Boolean được đặt true nếu thiết bị của người dùng có nhiều hơn một camera.
- **_multiCameraIndex_**: Chỉ số của camera mà view nên render.
- **_videoAspect_**: Tỷ lệ khung hình của video.
- **_fullScreen_**: Boolean xác định xem VideoView sẽ được render ở chế độ toàn màn hình hay danh sách cuộn ngang.

## Hướng Dẫn Quản Lý Âm Thanh, camera , micro, đèn flash trong Ứng Dụng Sử Dụng Video SDK

### 1. Quản lý âm thanh

#### 1.Kiểm Tra Trạng Thái Kết Nối Âm Thanh

Trước khi triển khai các điều khiển âm thanh, bạn cần kiểm tra xem người dùng đã kết nối với âm thanh hay chưa. Điều này có thể được thực hiện bằng cách lấy loại âm thanh của người dùng (VideoSDKAudioType) và kiểm tra các trạng thái âm thanh như bị tắt tiếng hoặc đang nói chuyện.

Đầu tiên chúng ta khai báo VideoSdkUser từ thư viện.

```dart
 VideoSdkUser mySelf = VideoSdkUser() ;
```

##### 1.1. Kiểm Tra Người Dùng Có Bị Tắt Tiếng

```dart
bool isMuted = mySelf.audioStatus.isMuted();
```

##### 1.2. Kiểm Tra Người Dùng Có Đang Nói Chuyện

```dart
bool isTalking = mySelf.audioStatus.isTalking();
```

##### 1.3. Kiểm Tra Người Dùng Có Kết Nối Âm Thanh

```dart
VideoSDKAudioType audioType = mySelf.audioStatus.getAudioType();
```

#### 2.Kết Nối Người Dùng với Âm Thanh

- Nếu người dùng chưa kết nối với âm thanh, bạn có thể kết nối họ bằng cách sử dụng VideoSDKAudioHelper.

- Đầu tiên là phải khai bao thư viện VideoSdk

```dart
    var videoSdk = VideoSdk();
```

##### 2.1 Kết Nối Âm Thanh

```dart
  videoSdk.audioHelper.startAudio();
```

##### 2.2 Tắt/Mở Âm Thanh Người Dùng

- Sau khi kết nối âm thanh, bạn có thể tắt hoặc mở âm thanh của người dùng bằng cách gọi các phương thức muteAudio và unmuteAudio.

##### 2.2.1 Tắt Âm Thanh Người Dùng

```dart
videoSdk.audioHelper.muteAudio(mySelf.userId);
```

##### 2.2.2 Mở Âm Thanh Người Dùng

```dart
videoSdk.audioHelper.unmuteAudio(mySelf.userId);
```

#### 3. Ngắt Kết Nối Âm Thanh

- Để ngắt kết nối hoàn toàn khỏi âm thanh, bạn có thể sử dụng phương thức stopAudio.

```dart
videoSdk.audioHelper.stopAudio();
```

#### 4.Tùy Chọn Âm Thanh Nâng Cao

- Video SDK sử dụng các công nghệ như giảm nhiễu và loại bỏ tiếng vọng để cải thiện chất lượng âm thanh. Tuy nhiên, trong một số tình huống, bạn có thể muốn tắt các bộ lọc này để thu âm thanh gốc từ micro, ví dụ như sử dụng micro chất lượng cao có bộ lọc âm thanh tích hợp hoặc để thu âm thanh toàn diện mà không cần giảm nhiễu.

##### 4.1 Bật Âm Thanh Gốc

- Để bật âm thanh gốc, bạn cần đặt enableMicOriginalInput thành true trong lớp VideoSdkAudioSettingHelper. Mặc định, giá trị này là false.

```dart
var videoSdk = VideoSdk();
await videoSdk.audioSettingHelper.enableMicOriginalInput(true);
```

##### 4.2 Tắt Âm Thanh Gốc

- Nếu bạn muốn tắt âm thanh gốc và bật lại các bộ lọc âm thanh mặc định, đặt enableMicOriginalInput thành false.

```dart
await videoSdk.audioSettingHelper.enableMicOriginalInput(false);
```

### 2. Quản lý camera

- #### 2.1 Bật tắc (On/Off) camera (startVideo)

```dart
var videoIdbRoomController = VideoSdkChatRoomManager();
await videoIdbRoomController.toggleCamera();
```

- #### 2.2 Swich camera (Hoán đổi ống kính camera)

```dart
var videoSdk = VideoSdk();
 await videoSdk.videoHelper.switchCamera(null);
```

- #### 2.3 Bật tắt Mirror video (lật video)

```dart
  await videoSdk.videoHelper
                      .mirrorMyVideo(true),
```

### 3. Quản lý microphone

- Bật /Tắt microphone

```dart
  await videoSdk.audioSettingHelper
                .enableMicOriginalInput(true);
```

- Lấy ra biến bật/tắt microphone

```dart
var isMicOn =
                await videoSdk.audioSettingHelper.isMicOriginalInputEnable();
```

### 4. Quản lý đèn flashlight

- Bật/ Tắt flashlight trên ios

```dart
var videoSdk = VideoSdk();
 await videoSdk.videoHelper.toggleFlashlight();
```

- Lấy giá trị flashlight trên ios

````dart
var videoSdk = VideoSdk();
bool isFlashLightIosOn = await videoSdk.videoHelper.getFlashlightStatus();
```


- Bật/tắt flashlight trên android

```dart
  var videoSdk = VideoSdk();
  await videoSdk.videoHelper.turnOnOrOffFlashlight(true);
````

- Lấy giá trị flashlight trên android

```dart
bool isFlashlightOn = await videoSdk.videoHelper.isFlashlightOn();
```

### 5. Quản lý pip mode in android (do android phải setup riêng , IOS đã được hỗ trợ sẵn)

```dart
var videoSdk = VideoSdk();

videoSdk.initPipModeForAndroid();
```

## 5.Hướng Dẫn Sử Dụng Tính Năng Chat trong Ứng Dụng Sử dụng Video SDK

### 1. Các Thành Phần Chính của Video SDK cho Chat

- Để triển khai tính năng chat trong ứng dụng, bạn cần làm quen với hai thành phần chính sau đây trong Video SDK:

- **chatNewMessageNotify** Event: Sự kiện này được kích hoạt khi có tin nhắn mới được gửi hoặc nhận. Callback này xác nhận việc giao hàng của tin nhắn.

- **VideoSDKChatHelper**: Một đối tượng cung cấp các phương thức để gửi và nhận tin nhắn trong phiên gọi đang chạy trên ứng dụng của bạn.

### 2. Gửi tin nhắn

- Trong một phiên gọi, có hai hình thức chat chính: công khai và riêng tư.

#### 2.1 Tin Nhắn Riêng Tư

- Tin nhắn riêng tư được gửi đến một người dùng cụ thể trong phiên gọi.

**Các bước triển khai:**

- 1. Kiểm Tra Tính Năng Chat Riêng Tư Được Bật: Trước khi gửi tin nhắn riêng tư, bạn cần kiểm tra xem tính năng chat riêng tư có được bật trong phiên gọi hay không.

```dart
bool isChatDisabled = videoSdk.chatHelper.isChatDisabled;
```

- 2. Gửi Tin Nhắn Riêng Tư: Nếu tính năng chat riêng tư được bật, bạn có thể gửi tin nhắn đến một người dùng cụ thể bằng cách sử dụng phương thức sendChatToUser.

```dart

if (videoSdk.chatHelper.isPrivateChatDisabled()) {
  // Không thể gửi tin nhắn riêng tư
} else {
  videoSdk.chatHelper.sendChatToUser(user.userId, "Đây là một tin nhắn riêng tư");
}

```

#### 2.2 Tin Nhắn Công Khai

- Tin nhắn công khai được gửi đến tất cả các người dùng hiện có trong phiên họp.

**Các Bước Triển Khai:**

- **Gửi Tin Nhắn Công Khai**: Sử dụng phương thức sendChatToAll để gửi tin nhắn đến tất cả các người tham gia trong phiên họp.

```dart
videoSdk.chatHelper.sendChatToAll("Đây là một tin nhắn công khai");
```

### 3. Nhận Tin Nhắn

- Khi có tin nhắn mới được gửi hoặc nhận trong phiên họp, bạn cần xử lý sự kiện này để hiển thị tin nhắn cho người dùng.

#### 5.3.1. Đăng Ký Sự Kiện Nhận Tin Nhắn Mới

- Khởi tạo manager room chat thuộc thư viện

```dart
final VideoSdkChatRoomManager videoSdkChatRoomManager;
```

- Sử dụng hàm **receivedMessage()** để listen tin nhắn khi có user gửi tới

```dart
videoSdkChatRoomManager.receivedMessage(emitter,
          onReceived: (VideoSdkChatMessage message) {
        VideoSdkChatMessage newMessage =
            VideoSdkChatMessage.fromJson(jsonDecode(message.toString()));
            var content = message.content;
            var sender = message.senderUser;
            var senderName = sender.userName;
            chatMessages.value.add(newMessage);
            messageLength.value += 1;
            if (listScrollController.hasClients) {
              listScrollController
                  .jumpTo(listScrollController.position.maxScrollExtent);
            }
      });
```

#### 5.3.2 Xử Lý Thông Tin Tin Nhắn

- Khi nhận được tin nhắn mới, bạn cần lấy các thông tin quan trọng như người gửi và nội dung tin nhắn để hiển thị trong giao diện người dùng.

- sender.userName: Tên của người gửi.
- message.content: Nội dung của tin nhắn.

### 4. Định Nghĩa Các Thuộc Tính của Tin Nhắn

Khi làm việc với VideoSDKChatMessage, bạn cần lưu ý các thuộc tính sau:

messageItem.isChatToAll: Trả về false đối với tin nhắn riêng tư và true đối với tin nhắn công khai.
messageItem.isSelfSend: Trả về true nếu tin nhắn được gửi bởi người dùng hiện tại.
messageItem.timestamp: Thời gian gửi tin nhắn.
messageItem.receiverUser: Người nhận của tin nhắn riêng tư.

================================================================

## 6. Hướng Dẫn Thiết Lập và Sử Dụng Command Channel trong Ứng Dụng Sử dụng Video SDK

- Command Channel trong Video SDK cung cấp một phương thức hiệu quả để giao tiếp giữa các thành phần trong ứng dụng của bạn mà không phụ thuộc vào hệ thống chat. Việc sử dụng Command Channel thay vì gửi lệnh thông qua chat giúp tách biệt các mối quan tâm, tránh vượt quá giới hạn tần suất gửi tin nhắn, và giảm khả năng gặp lỗi.
- **Các Tính Năng Chính của Command Channel:**

  - Phản ứng thời gian thực đối với nội dung trực tiếp.
  - Truy cập các cài đặt trong ứng dụng của bạn.
  - Cập nhật trạng thái cho các mô hình chia sẻ như trò chơi bàn.

    **Lưu Ý:**

    - Kích thước tối đa mỗi lệnh: 512 ký tự.
    - Giới hạn tần suất: 35 lệnh mỗi giây.

### 1. Các Thành Phần Chính của Command Channel

- Để sử dụng Command Channel, bạn cần làm quen với các thành phần chính sau đây trong Video SDK:

**VideoSDKCmdChannel:** Đối tượng chính để tương tác với Command Channel.
Sự kiện **onCommandChannelConnectResult**: Xác nhận kết nối của Command Channel.
Phương thức **sendCommand**: Gửi lệnh đến người dùng cụ thể hoặc toàn bộ phiên họp.
Sự kiện **onCommandReceived**: Nhận lệnh từ các người dùng khác.

### 2. Các Bước Thiết Lập Command Channel

#### 2.1 Lấy Instance của Command Channel

- Trước tiên, bạn cần lấy một instance của VideoSDKCmdChannel từ đối tượng video SDK hiện tại.

```dart
final VideoSdk videoSdk = VideoSdk();
late VideoSDKCmdChannel cmdChannel;
```

- Bước 2: Khởi tạo biến

```dart
 // Lấy instance của Command Channel
    cmdChannel = videoSdk.cmdChannel;

    // Đăng ký sự kiện kết nối Command Channel
    videoSdk.emitter.on(EventType.onCommandChannelConnectResult, (data) {
      _handleCommandChannelConnectResult(data);
    });

    // Đăng ký sự kiện nhận lệnh
    videoSdk.emitter.on(EventType.onCommandReceived, (data) {
      _handleCommandReceived(data);
    });
```

- Bước 3 : Hủy đăng ký sự kiện khi widget bị dispose

```dart
    videoSdk.emitter.off(EventType.onCommandChannelConnectResult);
    videoSdk.emitter.off(EventType.onCommandReceived);
```

#### 2.2 Chờ Command Channel Trở Thành Hoạt Động

- Sau khi kết nối, bạn cần đợi Command Channel trở thành hoạt động. Điều này được xác nhận thông qua callback onCommandChannelConnectResult.

```dart
final commandChannelConnectResult =
    videoSdk.emitter.on(EventType.onCommandChannelConnectResult, (data) async {
        data = data as Map;
        if(data['success']) {
            // Command Channel đã kết nối thành công
        }
    });
```

#### 2.3 Gửi Lệnh

- Sau khi Command Channel đã kết nối, bạn có thể gửi lệnh thông qua phương thức sendCommand. Bạn có thể gửi lệnh đến một người dùng cụ thể hoặc toàn bộ phiên gọi.

##### 2.3.1 Gửi Lệnh đến Người Dùng Cụ Thể

```dart
// Gửi lệnh "raise_hand" đến người dùng có userId cụ thể
await cmdChannel.sendCommand(userId, "raise_hand");
```

##### 2.3.2 Gửi Lệnh đến Toàn Bộ Phiên gọi

```dart
// Gửi lệnh "lower_all_hands" đến tất cả người dùng trong phiên họp
await cmdChannel.sendCommand(null, "lower_all_hands");
```

#### 2.4 Nhận Lệnh

- Khi một lệnh được gửi đến bạn, sự kiện onCommandReceived sẽ được kích hoạt. Bạn có thể xử lý lệnh này theo nhu cầu của ứng dụng.

```dart
final commandReceived =
    videoSdk.emitter.on(EventType.onCommandReceived, (data) async {
        data = data as Map;
        VideoSdkUser sender = VideoSdkUser.fromJson(jsonDecode(data['sender']));
        String command = data['command'];
        debugPrint("Sender: ${sender.userName}, Command: $command");

        // Xử lý lệnh nhận được
        // Ví dụ: Nếu lệnh là "raise_hand", hiển thị biểu tượng tay giơ lên
    });
```

================================================================

## 7. Hướng dẫn setup chức năng share màn hình cho dự án

- **iOS platform**

### 1. Giới Thiệu

- Chia sẻ màn hình trong Video SDK cung cấp hai phương pháp chính để chia sẻ nội dung màn hình:

- **Broadcast màn hình thiết bị**: Sử dụng ZoomVideoSDKScreenShare.xcframework, ReplayKit và các framework video của Apple để chia sẻ toàn bộ màn hình thiết bị trong phiên họp.

- **Chia sẻ một UIView**: Chia sẻ một UIView cụ thể trong phiên họp.

Chia sẻ một UIView: Chia sẻ một UIView cụ thể trong phiên họp.
Cả hai phương pháp này đều yêu cầu sử dụng CptShare.xcframework.

![Broadcast Type](assets/broadcast_type.png "Broadcast type")

### 2. Các Bước Triển Khai Broadcast Màn Hình Thiết Bị

- Phần này hướng dẫn bạn cách kích hoạt và bắt đầu phát sóng màn hình của người dùng trong phiên họp sử dụng ReplayKit và Video SDK.

#### 2.1. Yêu Cầu Trước Khi Bắt Đầu

- Trước khi bắt đầu, bạn cần đảm bảo rằng:

- Bạn hiểu rõ về Broadcast Extensions, App Group IDs và ReplayKit. Video sdk sử dụng các công nghệ này cùng với các framework video của Apple để triển khai chia sẻ màn hình.

#### 2.2. Tạo Một Target Mới

- Tạo Broadcast Upload Extension:

- Mở Xcode và chọn File > New > Target.
  Chọn Broadcast Upload Extension trong tab iOS và nhấn Next.
  Đặt tên cho target mới, ví dụ ScreenShare, chọn ngôn ngữ mong muốn và nhấn Finish.
  Nếu được nhắc kích hoạt scheme, nhấn Activate.

=======================

**Cấu Hình Podfile cho Dự Án iOS**

Để cấu hình Podfile cho dự án iOS của bạn, hãy thêm đoạn mã sau vào file Podfile trong thư mục ios của dự án:

```ruby
platform :ios, '13.0'

target 'Runner' do
  # Sử dụng frameworks và headers module
  use_modular_headers!

  flutter_install_all_ios_pods File.dirname(File.realpath(__FILE__))

  target 'RunnerTests' do
    inherit! :search_paths
  end
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    flutter_additional_ios_build_settings(target)
    target.build_configurations.each do |config|
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      # Khắc phục lỗi https://github.com/flutter/flutter/issues/64502
      config.build_settings['ONLY_ACTIVE_ARCH'] = 'NO' # <= dòng này
    end
  end
end
```

===================================================================================

**Thêm Đường Dẫn Vào Dự Án Xcode**
Thêm đường dẫn vào cài đặt của extension Broadcast:

Mở extension Broadcast trong Xcode.

Thêm đường dẫn sau vào phần "Objective-C Bridging Header" , "Header Search Paths", "System Header Search Paths":

```ruby
$(PROJECT_DIR)/${name_extension_folder}/Broadcast-Bridging-Header.h
```

===================================================================================

```xml
	<key>UIBackgroundModes</key>
	<array>
		<string>audio</string>
		<string>fetch</string>
		<string>picture-in-picture</string>
		<string>voip</string>
	</array>
	<key>RTCAppGroupIdentifier</key>
	<string>group.com.idb.videocall.app</string>
	<key>RTCScreenSharingExtension</key>
	<string>com.idb.videocall.BroadcastExtension</string>
	<key>NSBluetoothPeripheralUsageDescription</key>
	<string>bluetoothDecription</string>
	<key>NSCameraUsageDescription</key>
	<string>cameraDesciption</string>
	<key>NSMicrophoneUsageDescription</key>
	<string>microphoneDesciption</string>
	<key>NSPhotoLibraryUsageDescription</key>
	<string>photoLibraryDescription</string>
```

**Add các permission này vào file info.plist thuộc Broadcast extension**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>NSExtension</key>
	<dict>
		<key>NSExtensionAttributes</key>
		<dict>
			<key>RPBroadcastExtensionPointIdentifier</key>
			<string>com.apple.broadcast-services-upload</string>
		</dict>
		<key>NSExtensionPointIdentifier</key>
		<string>com.apple.broadcast-services-upload</string>
		<key>NSExtensionPrincipalClass</key>
		<string>$(PRODUCT_MODULE_NAME).SampleHandler</string>
		<key>RPBroadcastProcessMode</key>
		<string>RPBroadcastProcessModeSampleBuffer</string>
		<key>RTCAppGroupIdentifier</key>
		<string>group.com.idb.videocall.app</string>
		<key>RTCScreenSharingExtension</key>
		<string>com.idb.videocall.BroadcastExtension</string>
	</dict>
</dict>
</plist>
```

===================================================================================

**Tích hợp ZoomVideoSDKScreenShare với thư viện C++**

- ZoomVideoSDKScreenShare framework sử dụng các thư viện C++, vì vậy để làm cho dự án của bạn tương thích với những thư viện này, bạn cần thực hiện các thay đổi sau trong mục tiêu ScreenShare:

Nếu bạn đang sử dụng Objective-C:
Điều hướng đến ScreenShare -> SampleHandler.m và đổi tên tệp thành SampleHandler.mm.

Nếu bạn đang sử dụng Swift:
Điều hướng đến ScreenShare target -> Build Settings -> Other Linker Flags và thêm giá trị “-lc++”.

===================================================================================
**Tích hợp AppGroudId vào dự án**

1. Cài đặt App Groups:

Sử dụng App Groups để thiết lập liên lạc giữa mục tiêu chia sẻ màn hình (ScreenShare target) và mục tiêu chính của ứng dụng của bạn.

2. Bật App Groups:

Truy cập vào mục tiêu chính của ứng dụng của bạn:
Mở Xcode -> Target của ứng dụng -> Signing and Capabilities -> Nhấn + Capability và chọn App Groups.

3. Tạo App Group:

Nhấp vào biểu tượng “+” ở cuối phần App Groups để tạo một App Group mới trong mục tiêu chính và đặt tên cho nó. Tên này sẽ là App Group ID. Tương tự như Bundle ID, App Group ID được sắp xếp theo thứ tự ngược của tên miền và bắt đầu với “group.”.

Chúng tôi khuyến khích thêm Bundle ID của bạn vào sau “group.” để tạo App Group ID vì điều này giúp dễ dàng quản lý. Hình ảnh dưới đây là ví dụ về cách một App Group ID có thể trông như thế nào. Bạn phải tạo riêng cho mình một App Group ID duy nhất.

4. Kích hoạt App Group:

Sau khi tạo App Group, bạn tích vào ô bên cạnh App Group ID để kích hoạt App Group này.

Lặp lại các bước trên cho mục tiêu chia sẻ màn hình
Thực hiện lại các bước trên để kích hoạt cùng App Group trong mục tiêu Screenshare extension. Lưu ý rằng phải sử dụng cùng một App Group ID cho cả hai mục tiêu.

5. Cấu hình App Group cho Video SDK:

Sau khi hoàn thành các bước trên, điều hướng đến đoạn mã nơi bạn khởi tạo Video SDK trong ứng dụng và truyền App Group ID vào đối tượng SDKInitContext của bạn.

### **Cập Nhật File SampleHandler.swift cho Extension Broadcast Upload**

#### **Thay thế nội dung của file SampleHandler.swift trong extension Broadcast upload bằng đoạn mã sau:**

```swift
import Foundation
import ReplayKit

class SampleHandler: RPBroadcastSampleHandler, ZoomVideoSDKScreenShareServiceDelegate {
    var screenShareService: ZoomVideoSDKScreenShareService?

    override init() {
        super.init()
        // Tạo instance của ZoomVideoSDKScreenShareService để xử lý các hành động broadcast.
        let params = ZoomVideoSDKScreenShareServiceInitParams()
        // Cung cấp ID nhóm ứng dụng từ tài khoản Apple Developer của bạn.
        params.appGroupId = "your app group ID here"
        // Đặt giá trị này là true để kích hoạt chia sẻ âm thanh thiết bị trong quá trình chia sẻ màn hình.
        params.isWithDeviceAudio = true
        let service = ZoomVideoSDKScreenShareService(params: params)
        self.screenShareService = service
        screenShareService?.delegate = self
    }

    override func broadcastStarted(withSetupInfo setupInfo: [String : NSObject]?) {
        guard let setupInfo = setupInfo else { return }
        // Truyền thông tin thiết lập cho SDK.
        screenShareService?.broadcastStarted(withSetupInfo: setupInfo)
    }

    override func broadcastPaused() {
        // Thông báo cho SDK rằng broadcast đã bị tạm dừng.
        screenShareService?.broadcastPaused()
    }

    override func broadcastResumed() {
        // Thông báo cho SDK rằng broadcast đã tiếp tục.
        screenShareService?.broadcastResumed()
    }

    override func broadcastFinished() {
        // Thông báo cho SDK rằng broadcast đã kết thúc.
        screenShareService?.broadcastFinished()
    }

    override func processSampleBuffer(_ sampleBuffer: CMSampleBuffer, with sampleBufferType: RPSampleBufferType) {
        // Truyền sample buffer vào SDK.
        screenShareService?.processSampleBuffer(sampleBuffer, with: sampleBufferType)
    }

    func zoomVideoSDKScreenShareServiceFinishBroadcastWithError(_ error: Error?) {
        guard let error = error else { return }
        // Kết thúc broadcast khi nhận được lỗi từ SDK.
        finishBroadcastWithError(error)
    }
}
```

- **Android platform**

- Thêm 2 permission này trong file AndroidManifest

```xml
	<uses-permission android:name="android.permission.FOREGROUND_SERVICE" />
	<uses-permission android:name="android.permission.REQUEST_IGNORE_BATTERY_OPTIMIZATIONS" />
```

- Thêm service này trong file AndroidManifest (nằm trong thẻ Application)

```xml
		<service android:name="com.example.videosdk_idb.NotificationService" android:enabled="true" android:exported="false" android:foregroundServiceType="mediaProjection" />
```

- Trong file build.gradle (trong thư mục app), thêm các đoạn code này

```gradle
dependencies {
    implementation project(':videosdk_idb')
}
```

- Trong file MainActivity.kt, thêm đoạn code này để cấu hình cho chức năng share màn hình

```kotlin
package com.example.videocall_app3

import android.content.Intent
import android.content.res.Configuration
import android.os.Bundle
import com.example.videosdk_idb.*
import io.flutter.embedding.android.FlutterActivity

class MainActivity : FlutterActivity() {

    // Biến screenShareManager sẽ quản lý chức năng chia sẻ màn hình
    private lateinit var screenShareManager: ScreenShareManager

    // Phương thức onCreate được gọi khi Activity được tạo
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Khởi tạo screenShareManager với ngữ cảnh là MainActivity
        screenShareManager = ScreenShareManager(this)
    }

    // Phương thức onActivityResult được gọi khi có kết quả trả về từ một Activity khác
    override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
        // Gọi phương thức onActivityResult từ lớp cha để xử lý các hoạt động chung
        super.onActivityResult(requestCode, resultCode, data)

        // Chuyển xử lý kết quả cho screenShareManager
        // Phương thức handleActivityResult sẽ xử lý việc bắt đầu chia sẻ màn hình
        screenShareManager.handleActivityResult(requestCode, resultCode, data)
    }

    override fun onUserLeaveHint() {
        super.onUserLeaveHint()
        // Notify the plugin about onUserLeaveHint
        // Post a delayed task to enter PiP mode
        activity?.window?.decorView?.post {
            VideosdkIdbPlugin.onUserLeaveHint()
        }

    }

    override fun onPictureInPictureModeChanged(
        isInPictureInPictureMode: Boolean,
        newConfig: Configuration
    ) {
        super.onPictureInPictureModeChanged(isInPictureInPictureMode, newConfig)
        // Notify the plugin about PiP mode change
        VideosdkIdbPlugin.onPictureInPictureModeChanged(isInPictureInPictureMode)
    }

}
```

- **Flutter**

## 1. Lấy Instance của VideoSDKShareHelper:

```dart
var shareHelper = await videoSdk.shareHelper;
```

## 2. Kiểm Tra Trạng Thái Chia Sẻ:

```dart
var isOtherSharing = await shareHelper.isOtherSharing();
var isShareLocked = await shareHelper.isShareLocked();

if (isOtherSharing) {
  showDialog<String>(
    context: context,
    builder: (BuildContext context) => AlertDialog(
      title: const Text("Error"),
      content: const Text('Other is sharing'),
      actions: <Widget>[
        TextButton(
          onPressed: () => Navigator.pop(context, 'OK'),
          child: const Text('OK'),
        ),
      ],
    ),
  );
} else if (isShareLocked) {
  showDialog<String>(
    context: context,
    builder: (BuildContext context) => AlertDialog(
      title: const Text("Error"),
      content: const Text('Share is locked by host'),
      actions: <Widget>[
        TextButton(
          onPressed: () => Navigator.pop(context, 'OK'),
          child: const Text('OK'),
        ),
      ],
    ),
  );
}

```

## 3 .Gửi Lệnh Chia Sẻ Màn Hình:

```dart
if (isSharing.value) {
  zoom.shareHelper.stopShare();
} else {
  zoom.shareHelper.shareScreen();
}
```

## 4.Thêm Callbacks để Theo Dõi Trạng Thái Chia Sẻ

### 4.1. Tạo và Đăng Ký Event Listener:

```dart
var eventListener = VideoSdkEventListener();
eventListener.addEventListener();
EventEmitter emitter = eventListener.eventEmitter;

final userShareStatusChangeListener =
  emitter.on(EventType.onUserShareStatusChanged, (data) async {
    data = data as Map;
    VideoSdkUser? mySelf = await zoom.session.getMySelf();
    VideoSdkUser shareUser =
      VideoSdkUser.fromJson(jsonDecode(data['user'].toString()));

    if (data['status'] == ShareStatus.Start) {
      sharingUser.value = shareUser;
      fullScreenUser.value = shareUser;
      isSharing.value = (shareUser.userId == mySelf?.userId);
    } else {
      sharingUser.value = null;
      isSharing.value = false;
      fullScreenUser.value = mySelf;
    }
  });

```
