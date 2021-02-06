+++
title = "Agent Not Running"
date = 2020
weight = 1
chapter = false
pre = "<b>7.1. </b>"
+++

**Contents:**
- [Trường hợp gặp phải](#trường-hợp-gặp-phải)
- [Kiểm tra hoạt động](#kiểm-tra-hoạt-động)
- [Hướng xử lý](#hướng-xử-lý)

#### Trường hợp gặp phải
- **Hệ điều hành:** Windows
- **Lỗi hiển thị:** Dừng tại bước **"Establish communication between the CloudEndure Agent and the Replication Server."**
![CloudEndure](../../../images/7/1.png?width=30pc)

- Một số trường hợp khác:
{{% notice info %}}
Ở trạng thái thiết lập quá trình replication. Tình trạng bị dừng tại trạng thái màu đỏ **"Establish communication between the…"** ở giao diện console.
![CloudEndure](../../../images/7/2.png?width=30pc)
{{% /notice %}}

{{% notice info %}}
Ở trạng thái thiết lập quá trình replication. Tình trạng bị dừng tại trạng thái màu đỏ **"Communication with Source machine lost"** ở giao diện console.
![CloudEndure](../../../images/7/2.png?width=30pc)
{{% /notice %}}

Chung quy lại vấn đề chúng ta có thể gặp phải đó là tình trạng CloudEndure Agent không khởi chạy lên được khiến cho quá trình Staging không thể tiến hành.

#### Kiểm tra hoạt động
**Kiểm tra hoạt động Service:**

Sau khi chạy trình cài đặt CloudEndure lên máy, để xác định lỗi xảy ra, chúng ta có thể kiểm tra như sau:
- Mở cửa sổ **Task Manager** trên máy tính chạy hệ điều hành Windows.
- Chọn tab **Services** để hiển thị danh sách các Service.
- Kiểm tra trạng thái dịch vụ CloudEndure Agent.
  - Trạng thái của dịch vụ có thể đang là **Stopped**.
  - Cột **PID** không có thông tin.
- Hãy thử chuột phải vào dịch vụ, chọn **Start** để khởi chạy.
- Trường hợp sau khi khởi chạy, dịch vụ chuyển trạng thái sang **Running** sau đó chuyển lại thành **Stopped**. Rất có thể chúng ta đã gặp vấn đề với dịch vụ trên Windows.

**Kiểm tra nhật kí hoạt động của CloudEndure Agent:**

Để kiểm tra nhật ký hoạt động của Agent, ta tìm đến tập tin ```C:\Program Files (x86)\CloudEndure\agent.log.0```
Hãy kiểm tra nội dung nhật ký so với nội dung bên dưới.

```text
{"message":"Boot device 'c:0' is missing from volume map","log":{"type":"Remote","name":"Agent","level":"ERROR","level_number":40},"source_code":{"function":"removeDuplicatedVolumes","file":"com.cloudendure.agent.platform.HardwareInfoGetterWindows"},"runtime_thread":21,"origin":{"hostname":"host"},"@timestamp":"2020-04-21T05:59:32.258Z"}>>>
{"message":"Creating SourceNetworkCfg folder","log":{"type":"Remote","name":"Agent","level":"ERROR","level_number":40},"source_code":{"function":"storeCurrentTcpipSettings","file":"com.cloudendure.agent.platform.HardwareInfoGetterWindows"},"runtime_thread":21,"origin":{"hostname":"host"},"@timestamp":"2020-04-21T05:59:32.291Z"}>>>
{"message":"Load module failed","log":{"type":"Remote","name":"Agent","level":"ERROR","level_number":40},"source_code":{"function":"load","file":"com.cloudendure.agent.TraceDriverAdapter"},"runtime_thread":17,"origin":{"hostname":"host"},"@timestamp":"2020-04-21T06:00:22.243Z"}>>>
{"message":"Changing volumes {0} failed","log":{"type":"Remote","name":"Agent","level":"WARNING","level_number":30},"source_code":{"function":"changeVolumes","file":"com.cloudendure.agent.VolumesChanger"},"runtime_thread":17,"args":["[name: \\\\?\\PhysicalDrive0, size: 192199786496]"],"origin":{"hostname":"host"},"@timestamp":"2020-04-21T06:00:22.244Z"}>>>
{"message":"Error changing volumes","log":{"type":"Remote","name":"Agent","level":"ERROR","level_number":40},"source_code":{"line":69,"function":"getChannel","file":"com.cloudendure.agent.ClientCommunicator"},"runtime_thread":17,"exception":{"message":"java.io.IOException: loadDriver failed with error code 577, stderr: "System error 577 has occurred.\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n", stdout: "\nC:\\Program Files (x86)\\CloudEndure>echo off \n[SC] StartService FAILED 577:\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n"","type":"com.cloudendure.agent.VolumesChanger$VolumeChangeException","trace":"com.cloudendure.agent.VolumesChanger$VolumeChangeException: java.io.IOException: loadDriver failed with error code 577, stderr: "System error 577 has occurred.\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n", stdout: "\nC:\\Program Files (x86)\\CloudEndure>echo off \n[SC] StartService FAILED 577:\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n"\r\n\tat com.cloudendure.agent.VolumesChanger.changeVolumes(VolumesChanger.java:69)\r\n\tat com.cloudendure.agent.ClientCommunicator.getChannel(ClientCommunicator.java:229)\r\n\tat com.cloudendure.agent.ClientCommunicator.receive(ClientCommunicator.java:334)\r\n\tat com.cloudendure.agent.ClientMessageHandler.run(ClientMessageHandler.java:66)\r\nCaused by: java.io.IOException: loadDriver failed with error code 577, stderr: "System error 577 has occurred.\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n", stdout: "\nC:\\Program Files (x86)\\CloudEndure>echo off \n[SC] StartService FAILED 577:\n\nWindows cannot verify the digital signature for this file. A recent hardware or software change might have installed a file that is signed incorrectly or damaged, or that might be malicious software from an unknown source.\n\n"\r\n\tat com.cloudendure.common.ProcessUtils.runCommand(ProcessUtils.java:121)\r\n\tat com.cloudendure.common.ProcessUtils.runShellCommand(ProcessUtils.java:84)\r\n\tat com.cloudendure.agent.TraceDriverAdapter.load(TraceDriverAdapter.java:245)\r\n\tat com.cloudendure.agent.AgentManager.start(AgentManager.java:962)\r\n\tat com.cloudendure.agent.VolumesChanger.changeVolumes(VolumesChanger.java:63)\r\n\t... 3 more\r\n"},"origin":{"hostname":"host"},"@timestamp":"2020-04-21T06:00:22.245Z"}>>>
```

#### Hướng xử lý
Trong trường hợp này, rất có thể CloudEndure Agent đã được cài đặt không thể hoạt động được khi Windows đang được khởi động ở chế độ **Secure Boot**.

**Sử dụng PowerShell để kiểm tra Secure Boot của Windows:**
```ps1
PS C:\WINDOWS\system32> Confirm-SecureBootUEFI
True
```

**Tắt Secure Boot:**
Trường hợp sử dụng Windows cài đặt trên máy vật lý: (Chi thiết hơn tại [Microsoft](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/disabling-secure-boot))
- Chọn **Start**, sau đó chọn **Settings**
- Chọn **Update and Security**
- Chọn **Recovery**
- Chọn vào **Restart now** ở trong **Advanced startup**
- Chọn **Troubleshoot**
- Chọn **Advanced options**
- Chọn **Startup Settings**
- Chọn vào **Restart**
- Nhấn phím số 7 trong **Startup Settings** để chọn **Disable driver signature enforcement**
- Khởi động lại máy.

Trường hợp sử dụng VMWare / ESXi, chúng ta sẽ phải tắt trong VM Configuration.
Sau dó hãy cài lại CloudEndure Agent.
