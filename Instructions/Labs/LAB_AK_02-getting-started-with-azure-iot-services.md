﻿---
lab:
    title: '实验室 02：Azure IoT 服务入门'
    module: '模块 1：IoT 和 Azure IoT 服务简介'
---

# Azure IoT 服务入门

## 实验室场景

你是为 Contoso（一家精制和分销美食奶酪的公司）工作的 Azure IoT 开发人员。你的任务是探索 Azure 和 Azure IoT 服务，这些服务将用于公司计划实施的 IoT 解决方案。你已熟悉 Azure 门户并为你的项目创建了资源组。现在，你需要开始调查 Azure IoT 服务。

## 本实验室概览

在本实验室中，你将开始探索用于为解决方案预配和连接 IoT 设备（IoT 中心和 IoT 中心设备预配服务）的 Azure IoT 服务。本实验室包括以下练习：

* 用唯一名称命名资源
* 使用 Azure 门户创建 IoT 中心
* 检查 IoT 中心服务的功能
* 创建设备预配服务并将其链接到 IoT 中心
* 检查设备预配服务的功能

## 实验室说明

### 练习 1：用唯一名称命名资源

在整个课程中，你将创建资源。为了确保实验室间的一致性，并帮助你在使用完资源后整理资源，我们将为你提供你应该使用的名称。但是，这些资源中的许多都公开了可在 Web 上使用的服务，这意味着它们必须具有全局唯一名称。为此，你将使用唯一标识符，该标识符将添加到资源名称的末尾。让我们创建你的唯一 ID。

#### 唯一 ID

唯一 ID 将由你的姓名首字母和当前日期构成，并使用以下模式：

```text
YourInitialsYYMMDD
```

因此，你的姓名首字母后跟本年的最后两位数字、当前数字月份和当前数字日期。这里有一些示例：

```text
GWB200123
BHO200504
CAH201216
DM200911
```

在某些情况下，可能会要求使用你唯一 ID 的小写版本：

```text
gwb200123
bho200504
cah201216
dm200911
```

当你希望使用自己的唯一 ID 时，会看到 `{YOUR-ID}`。你将用唯一值替换整个字符串（包括 `{}`）。

现在请记录你的唯一 ID，**请在整个课程期间使用同一数值** - ，不要每天更新日期。

让我们一起回顾部分资源示例以及与之关联的名称。

#### 资源组

资源组在订阅中必须具有唯一的名称；但是，该名称不必全局唯一。因此，在整个课程期间，你将使用以下资源组名称：**AZ-220-RG**。

  > **信息：** 资源组名称 - **AZ-220-RG**

#### 公共可见的资源

你创建的许多资源将具有可公开寻址（尽管受保护）的终结点，因此必须全局唯一。此类资源的示例包括 IoT 中心、设备预配服务和 Azure 存储帐户。对于其中的每一个，都将获得一个名称模板，并预期将 `{YOUR-ID}` 替换为你的唯一 ID。这里有一些示例：

如果你的唯一 ID 为：**CAH191216**

| 资源类型 | 名称模板 | 示例 |
| :--- | :--- | :--- |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ | AZ-220-HUB-CAH191216 |
| 设备预配服务 | AZ-220-DPS-_{YOUR-ID}_ | AZ-220-DPS-CAH191216 |
| Azure 存储帐户<br/>（名称必须小写且不含短划线） | az220storage_{YOUR-ID}_ | az220storagecah191216 |

你可能还需要更新 bash 脚本和 C＃源文件中的值，并将名称输入到 Azure 门户 UI 中。这里有一些示例：

```bash
#!/bin/bash

YourID="{YOUR-ID}"
RGName="AZ-220-RG"
IoTHubName="AZ-220-HUB-$YourID"

```

请注意，`YourID="{YOUR-ID}"` 应更新为 `YourID="CAH191216"` - 不要更改 `$YourID`。同样，在 C＃中，你可能会看到：

```csharp
private string _yourId = "{YOUR-ID}";
private string _rgName = "AZ-220-RG";
private string _iotHubName = $"AZ-220-HUB-{_yourId}";
```

同样，`private string _yourId = "{YOUR-ID}";` 应更新为 `private string _yourId = "CAH191216";` - 不要更改 `_yourId`。

### 练习 2：使用 Azure 门户创建 IoT 中心

Azure IoT 中心是一项完全托管的服务，可在 IoT 设备和 Azure 之间实现可靠、安全的双向通信。Azure IoT 中心服务提供以下内容：

* 与数十亿个 IoT 设备建立双向通信
* 有多种设备到云和云到设备通信选项，包括单向消息传递、文件传输和请求-答复方法。
* 内置声明性消息路由到其他 Azure 服务。
* 设备元数据和同步状态信息的可查询存储。
* 使用每个设备的安全密钥或 X.509 证书进行安全的通信和访问控制。
* 广泛监视设备连接性和设备标识管理事件。
* 适用于最受欢迎的语言和平台的 SDK 设备库。

你可以使用多种方法来创建 IoT 中心。例如，你可以使用 Azure 门户创建 IoT 中心资源，这是你将在任务中执行的操作。但是，你也可以编程方式创建 IoT 中心（和其他资源）。在本课程中，我们将研究可用于创建和管理 Azure 资源的其他方法，包括 Azure CLI 和 PowerShell。

#### 任务 1：使用 Azure 门户创建资源（IoT 中心）

1. 使用你的 Azure 帐户凭据登录到 [portal.azure.com](https://portal.azure.com)。

    如果有多个 Azure 帐户，请确保使用与该课程将使用的订阅绑定的帐户登录。  你可能会发现，使用 InPrivate/Incognito 浏览器会话最容易避免意外使用错误的帐户。

1. 请注意，已加载在上一个任务中创建的 AZ-220 仪表板。

    随着课程的进行，将向仪表板添加资源。

1. 在 Azure 门户菜单上，单击 **“+ 创建资源”**。

    Azure 市场是可在 Azure 中创建的所有资源的集合。市场中包含来自 Microsoft 和社区的资源。

1. 在“搜索”文本框中，输入 **“IoT”**，然后按下 **Enter**。

    > **注释**：由私人参与者提供的市场服务可能包括 Microsoft Azure Pass 或其他 Microsoft 信用产品/服务未涵盖的费用。

1. 在“搜索结果”边栏选项卡上，单击 **“IoT 中心”**。

    注意此边栏选项卡上显示的_有用链接_列表。

1. 请注意，在链接列表中，有一个指向“文档”的链接。

    现在无需浏览此文档，但是值得注意。“IoT 中心文档”__页面是 IoT 中心资源和文档的根页面。可以使用此页面浏览当前文档并找到可帮助你探索本课程范围之外的活动的教程和其他资源。在本课程中，可以参阅 docs.microsoft.com 站点，以获取有关特定主题的更多信息。

    如果确实打开了文档链接，请使用浏览器关闭“文档”选项卡，然后导航回“Azure 门户”选项卡。

#### 任务 2：使用所需的属性设置创建 IoT 中心

1. 单击 **“创建”**，开始创建新的 IoT 中心。

    >**提示：** 将来，还有另外两种方式可以获得_创建_任何 Azure 资源类型的体验：
        1. 如果收藏夹中有该服务，你可以单击该“服务”以导航到“实例列表”，然后单击顶部的“+ 添加”__按钮。
        2. 你可以在门户顶部的“搜索”__框中搜索服务名称来获取实例列表，然后单击顶部的“+ 添加”__按钮。

    接下来，你需要指定与中心和订阅有关的信息。以下步骤将引导你完成设置，并在你填充每个字段时逐一解释。

1. 在“IoT 中心”__边栏选项卡的“基本信息”__选项卡处，确保你打算在本课程中使用的 Azure **订阅**已选定。

1. 在 **“资源组”** 的右侧， 打开 **“选择现有项”** 下拉菜单，然后单击 **AZ-220-RG**

    这是你在上一个实验室中创建的资源组。将为此课程创建的资源分组在同一个资源组中。完成课程后，这可以帮助你清理资源。

1. 在 **“区域”** 的右侧，打开下拉列表并选择与资源组相同的区域。  确保其支持事件网格。

    正如之前所见，Azure 受到位于世界各地的众多数据中心支持。在 Azure 中创建内容时，你可以将其部署到这些数据中心位置中的其中一个位置。

    > **注释**：  有关支持事件网格的当前区域列表，请参见以下链接：[可用产品（按区域）](https://azure.microsoft.com/zh-cn/global-infrastructure/services/?products=event-grid&regions=all)

    > **注释**：  选取一个区域来托管应用时，请记住，选取靠近最终用户的区域会减少加载/响应时间。如果你与最终用户位于世界的两端，则不应选取距离你最近的区域。

1. 在 **“IoT 中心名称”** 右侧，为你的 IoT 中心输入全局唯一名称。

    要提供全局唯一名称，请输入 **AZ-220-HUB-_{YOUR-ID}_**（记住要将 **_{YOUR-ID}_** 替换为你在实验室 1 中创建的唯一 ID。）。

    例如：**AZ-220-HUB-CAH191021**

    IoT 中心的名称必须全局唯一，因为它是一种必须能够通过任何已连接 IP 的设备进行访问的公开访问资源。

    在你为新的 IoT 中心指定唯一名称时，请考虑以下事项：

    * 应用于_IoT 中心名称_的值在整个 Azure 中必须唯一。这是正确的，因为分配给该名称的值将在 IoT 中心的连接字符串中使用。由于 Azure 让你可以将世界各地的设备连接到中心中，因此必须使用连接字符串从 Internet 访问所有 Azure 中心，因而连接字符串必须唯一。我们稍后将在实验室探讨连接字符串。

    * 分配给_IoT 中心名称_的值在应用服务创建后便无法更改。如果确实需要更改名称，你需要新建一个 IoT 中心，重新注册你的设备，然后删除旧的 IoT 中心。

    * “IoT 中心名称”__字段是必填字段。

    > **注释**：  Azure 可确保你输入的名称是唯一的。如果你输入的名称不唯一，Azure 会在名称字段的末尾显示一个星号作为警告。你可以视需要在上面建议的名称中追加 '**-01**' 或 '**-02**'，以便实现全局唯一名称。

1. 在边栏选项卡顶部，单击 **“大小和规模”**。

    请花费片刻时间查看此边栏选项卡上显示的信息。

1. 在“定价和缩放层”右侧，打开下拉列表，然后选择 **“S1:标准层”**（如果尚未选择）。

    可以根据你需要的功能数以及每天通过解决方案发送的消息数从多个层级选项中进行选择。我们在本课程中使用的 _S1_ 层允许每个单位每天共计 400,000 条消息，并提供此训练所需的所有服务。实际上每日每个单位不需要 400,000 条消息，但是我们将使用此层级别提供的功能，例如_云到设备命令_、_设备管理_和 _IoT Edge_。IoT 中心还提供了用于测试和评估的免费层。它具有标准层的所有功能，但消息传递额度有限。但是，你不能从免费层升级到基本层或标准层。免费层适用于测试和评估。允许 500 台设备连接到 IoT 中心，每天最多可传输 8,000 条消息。每个 Azure 订阅可以在免费层中创建一个 IoT 中心。

    > **注释**：  _S1 - 标准_层的费用为每月每个单位 25.00 美元。我们将指定 1 个单位。有关其他层选项的详细信息，请参阅[为你的解决方案选择合适的 IoT 中心层](https://docs.microsoft.com/zh-cn/azure/iot-hub/iot-hub-scaling)。

1. 在 **“S1 IoT 中心单位数”** 右侧， 确保选择了 **“1”**。

    如上所述，你选择的定价层会建立你的中心每天每个单位可以处理的消息数。要增加你的中心可处理的消息数而无需移至更高的定价层，你可以增加单位数。例如，如果你希望 IoT 中心支持 800,000 条消息流入量，你可以选择 *“两个”* S1 层单位。对于 Microsoft 创建的 IoT 课程，将仅使用 1 个单位。

1. 在 **Azure 安全中心** 右侧， 确保选择了 **“关闭”**。

    Azure 安全中心统一了安全管理，并支持跨混合云工作负荷和 Azure IoT 解决方案进行端到端威胁检测和分析。我们会在稍后的实验室中浏览 Azure 安全中心，因此先暂时禁用此安全中心。目前，你可以通过 Azure 门户启用订阅级别的 Azure 安全中心。标准层在前 30 天免费。30 天后一旦使用，将按照[这里](https://azure.microsoft.com/zh-cn/pricing/details/security-center/)的详细定价方案自动收费。

1. 在_“高级设置”_下， 确保将 **“设备到云的分区”** 设置为 **“4”**。

    分区数将设备到云消息关联到这些消息的并行读取器的数目。大多数 IoT 中心仅需要四个分区，这是默认值。在本课程中，我们将使用默认分区数创建 IoT 中心。

1. 在边栏选项卡顶部，单击 **“查看 + 创建”**。

    花费片刻时间查看你提供的设置。

1. 在边栏选项卡底部，单击 **“创建”**，完成 IoT 中心的创建。

    部署可能需要一分钟或更长时间。你可以打开“Azure 门户通知”窗格来监视进度。

1. 请注意，几分钟后你会收到一条通知，指出 IoT 中心已成功部署到 **AZ-220-RG** 资源组。

1. 在 Azure 门户菜单中，单击 **“仪表板”**，然后单击 **“刷新”**。

    你会看到资源组磁贴列出新的 IoT 中心。

### 练习 3：检查 IoT 中心服务

正如我们已经指出的那样，IoT 中心是托管在云中的托管服务，充当中央消息中心，用于在你的 IoT 应用程序与其管理的设备之间进行双向通信。

IoT 中心的功能可帮助你生成可缩放的全功能 IoT 解决方案，例如管理制造业中使用的工业设备，跟踪医疗保健中的宝贵资产以及监控办公楼使用情况和其他更多场景。IoT 中心监视通过跟踪设备创建、设备故障和设备连接等事件，帮助你对解决方案的运行状况进行维护。

#### 任务 1：探索 IoT 中心“概述”边栏选项卡

1. 如有必要，使用 Azure 帐户凭据登录到 [portal.azure.com](https://portal.azure.com)。

    如果有多个 Azure 帐户，请确保使用与该课程将使用的订阅绑定的帐户登录。

1. 验证是否正在显示 AZ-220 仪表板。

1. 在 AZ-220-RG 资源组磁贴上，单击 **AZ-220-HUB-_{YOUR-ID}_**

    首次打开 IoT 中心时，将显示_“概述”_边栏选项卡。可以看到在边栏选项卡顶部区域提供了一些有关 IoT 中心服务的基本信息，例如数据中心位置和订阅。但此边栏选项卡也包含可提供如何使用中心和最近活动的相关信息的磁贴。在进一步探讨之前，我们先了解一下这些磁贴。

1. 在“概述”__边栏选项卡左下角处，请注意 **“IoT 中心的使用情况”** 磁贴。

    > **注释**：  磁贴根据浏览器的宽度进行流动，因此布局可能与描述有所不同。

    此磁贴提供了与中心连接的内容和消息计数的快速概述。当添加设备并开始发送消息时，此磁贴将提供出色的“概览”信息。

1. 请注意，_“IoT 中心使用情况”_磁贴右侧的 **“设备孪生操作”** 磁贴和 **“设备到云消息”** 磁贴。

    _“设备到云消息”_磁贴提供了一段时间内来自设备的传入消息的快速概述。你将在下一个模块中注册设备并向中心发送消息。

    本课程模块涵盖设备配置、设备预配和设备管理，其中你将学习设备孪生以及设备孪生操作。目前你只需知道在 IoT 中心注册的每个设备都有一个在你需要管理设备时可以使用的设备孪生。

#### 任务 2：使用导航菜单查看 IoT 中心的功能

1. 在“IoT 中心”边栏选项卡上，花一分钟时间审查左侧的导航菜单选项。

    如你所料，这些选项会打开可以访问 IoT 中心的属性和功能的边栏选项卡。它们让你能够访问连接到中心的设备。

1. 在左侧菜单的 **“资源管理器”** 下，单击 **“IoT 设备”**

    此边栏选项卡可用于添加、修改和删除注册到中心的设备。在课程结束时，你将非常熟悉此边栏选项卡。

1. 在左侧菜单顶部附近，单击 **“活动日志”**

    顾名思义，通过此边栏选项卡可以访问可用于查看活动和诊断问题的日志。还可以定义有助于日常任务的查询。非常方便。

1. 在左侧菜单的 **“设置”** 下，单击 **“内置终结点”**

    IoT 中心公开了启用外部连接的“终结点”。实质上，终结点是连接到 IoT 中心或与 IoT 中心通信的构造。你会看到你的中心已定义了两个终结点：

    * _事件_
    * _云到设备的消息传送_

1. 在左侧菜单的 **“消息传送”** 下，单击 **“消息路由”**

    使用 IoT 中心消息路由功能， 你可以将设备到云的传入消息路由到服务终结点，例如 Azure 存储容器、事件中心和服务总线队列。你还可以创建路由规则以执行基于查询的路由。

1. 在边栏选项卡顶部，单击 **“自定义终结点”**。

    自定义终结点（例如服务总线队列、Blob 存储和此处列出的其他终结点）通常在 IoT 实现中使用。

1. 花点时间查看 **“设置”** 下的菜单选项

    > **注释**：  本实验室练习仅用于介绍 IoT 中心服务并让你更加熟悉 UI，因此，如果你目前有点不知所措，请不要担心。随着本课程的继续进行，我们将引导你完成配置和管理 IoT 中心、设备和通信的过程。

### 练习 4：使用 Azure 门户创建设备预配服务

Azure IoT 中心设备预配服务是 IoT 中心的帮助程序服务，无需人工干预即可实现对适当 IoT 中心的零接触即时预配。设备预配服务提供以下内容：

* 零接触预配到单个 IoT 解决方案，而工厂没有硬编码 IoT 中心连接信息（初始设置）
* 跨多个中心的负载均衡设备
* 根据销售交易数据（多租户）将设备连接到其所有者的 IoT 解决方案
* 根据用例将设备连接到特定的 IoT 解决方案（解决方案隔离）
* 以最低的延迟将设备连接到 IoT 中心（地理分片）
* 根据设备的更改重新预配
* 滚动设备用于连接到 IoT 中心的密钥（不使用 X.509 证书进行连接时）

你可以使用多种方法来创建 IoT 中心设备预配服务的实例。例如，你可以使用 Azure 门户，这是你将在任务中执行的操作。但是，你也可以使用 Azure CLI 或 Azure 资源管理器模板创建 DPS 实例。

#### 任务 1：使用 Azure 门户创建资源（设备预配服务）

1. 如有必要，使用 Azure 帐户凭据登录到 [portal.azure.com](https://portal.azure.com)。

    如果有多个 Azure 帐户，请确保使用与该课程将使用的订阅绑定的帐户登录。

1. 在 Azure 门户菜单上，单击 **“+ 创建资源”**。

    Azure 市场是可在 Azure 中创建的所有资源的集合。市场中包含来自 Microsoft 和社区的资源。

1. 在“搜索”文本框中，键入 **“设备预配服务”**，然后按 Enter 键。

1. 在“搜索结果”边栏选项卡上，单击 **“IoT 中心设备预配服务”**。

    注意此边栏选项卡上显示的_有用链接_列表。

1. 请注意，在链接列表中，有一个指向“文档”的链接。

    同样，现在无需研究此文档，知道它可用就可以了。“IoT 中心设备预配服务文档”页面是 DPS 的根页面。可以使用此页面浏览当前文档并找到可帮助你探索本课程范围之外的活动的教程和其他资源。在本课程中，可以参阅 docs.microsoft.com 站点，以获取有关特定主题的更多信息。

    如果确实打开了文档链接，请使用浏览器关闭“文档”选项卡，然后导航回“Azure 门户”选项卡。

#### 任务 2：使用所需的属性设置创建设备预配服务

1. 单击 **“创建”**，开始创建新的 DPS 实例。

    接下来，你需要指定与中心和订阅有关的信息。以下步骤将引导你完成设置，并在你填充每个字段时逐一解释。

1. 在 **“名称”** 下，为你的设备预配服务输入唯一的名称。

    若要提供唯一名称，请输入 **AZ-220-DPS-_{YOUR-ID}_**。

    例如：**AZ-220-DPS-CAH191216**

1. 在 **“订阅”** 下，请确保已选择为本课程使用的订阅。

1. 在 **“资源组”** 下，打开 **“选择现有项”** 下拉菜单，然后单击 **AZ-220-RG**

    这是你在上一个实验室中创建的资源组。将为此课程创建的资源分组在同一个资源组中。完成课程后，这可以帮助你清理资源。

1. 在 **“位置”** 下，打开下拉列表，然后选择与资源组相同的区域。

    正如之前所见，Azure 受到位于世界各地的众多数据中心支持。在 Azure 中创建内容时，你可以将其部署到这些数据中心位置中的其中一个位置。

    > **注释**：  选取数据中心来托管应用时，请记住，选取靠近最终用户的数据中心会减少加载/响应时间。如果你与最终用户位于世界的两端，则不应选取离你最近的数据中心。

1. 在边栏选项卡底部，单击 **“创建”**。

    部署可能需要一分钟或更长时间。你可以打开“Azure 门户通知”窗格来监视进度。

1. 请注意，几分钟后你会收到一条通知，指出 IoT 中心设备预配服务实例已成功部署到 **AZ-220-RG** 资源组。

1. 在 Azure 门户菜单中，单击 **“仪表板”**，然后单击 **“刷新”**。

    你会看到“资源组”磁贴列出了新的 IoT 中心设备预配服务。

#### 任务 3：链接 IoT 中心和设备预配服务。

1. 请注意，AZ-220 仪表板同时列出了 IoT 中心和 DPS 资源。

    你会看到同时列出了 IoT 中心和 DPS 资源 -（如果资源是最近创建的，可能需要单击 **“刷新”**）

1. 在“资源组”磁贴上，单击 **“AZ-220-DPS-_{YOUR-ID}_”**。

1. 在“设备预配服务”__边栏选项卡的 **“设置”** 下，单击 **“链接的 IoT 中心”**。

1. 在边栏选项卡顶部，单击 **“+ 添加”**。

    将使用“将链接添加到 IoT 中心”__边栏选项卡提供将设备预配服务实例链接到 IoT 中心所需的信息。

1. 在“将链接添加到 IoT 中心”__边栏选项卡上，确保 **“订阅”** 下拉菜单显示的是将用于本课程的订阅。

    该订阅用于提供可用 IoT 中心的列表。

1. 打开 IoT 中心下拉菜单，然后单击 **AZ-220-HUB-_{YOUR-ID}_**。

    这是你在上一个练习中创建的 IoT 中心。

1. 在“访问策略”下拉列表中，单击 **“iothubowner”**。

    _iothubowner_ 凭据提供与指定的 IoT 中心建立链接所需的权限。

1. 若要完成配置，请单击 **“保存”**。

    现在你会看到在“链接的 IoT 中心”边栏选项卡上列出的所选中心。可能需要单击 **“刷新”** 来显示已链接的 IoT 中心。

1. 在“Azure 门户中心”菜单上，单击 **“仪表板”**。

### 练习 5：检查设备预配服务

IoT 中心设备预配服务是 IoT 中心的一项辅助服务，它支持对正确的 IoT 中心进行零接触即时预配，而无需人工干预，使客户能够以安全和可扩展的方式预配数百万台设备。

#### 任务 1：探索“设备预配服务概述”边栏选项卡

1. 如有必要，使用 Azure 帐户凭据登录到 [portal.azure.com](https://portal.azure.com)。

    如果有多个 Azure 帐户，请确保使用与该课程将使用的订阅绑定的帐户登录。

1. 验证是否正在显示 AZ-220 仪表板。

1. 在 _AZ-220-RG_ 资源组磁贴处，单击 **AZ-220-DPS-_{YOUR-ID}_**

    首次打开设备预配服务实例时，会显示“概述”__边栏选项卡。正如你所见，此边栏选项卡顶部的区域提供了一些有关 DPS 实例的基本信息，例如状态、数据中心位置和订阅。此边栏选项卡还提供了“快速链接”__部分，可访问：

    * [Azure IoT 中心设备预配服务文档](https://docs.microsoft.com/zh-cn/azure/iot-dps/)
    * [了解更多有关 IoT 中心设备预配服务的信息](https://docs.microsoft.com/zh-cn/azure/iot-dps/about-iot-dps)
    * [设备预配概念](https://docs.microsoft.com/zh-cn/azure/iot-dps/concepts-service)
    * [定价和缩放详细信息](https://azure.microsoft.com/zh-cn/pricing/details/iot-hub/)

    你可以浏览这些链接，了解更多信息。

#### 任务 2：使用导航菜单查看设备预配服务的功能

1. 花一分钟时间审查左侧的导航区域选项。

    如你所料，使用这些选项会打开边栏选项卡，其中可提供对 DPS 实例的活动日志、属性和功能的访问权限。

1. 在左侧菜单顶部附近，单击 **“活动日志”**

    顾名思义，通过此边栏选项卡可以访问可用于查看活动和诊断问题的日志。还可以定义有助于日常任务的查询。非常方便。

1. 在左侧导航区域的 **“设置”** 下，单击 **“快速入门”**。

    此边栏选项卡列出了开始使用 IoT 中心设备预配服务的步骤、文档链接以及用于配置 DPS 的其他边栏选项卡的快捷方式。

1. 在左侧导航区域的 **“设置”** 下，单击 **“共享访问策略”**。

    此边栏选项卡提供访问策略的管理，并列出现有策略和关联权限。

1. 在左侧导航区域的 **“设置”** 下，单击 **“链接的 IoT 中心”**。

    在此你可以看到之前链接的 IoT 中心。设备预配服务只能将设备预配到已与其链接的 IoT 中心。将 IoT 中心链接到设备预配服务的实例可为该服务提供对 IoT 中心的设备注册表的读/写权限；通过该链接，设备预配服务可以注册设备 ID 并在设备孪生中设置初始配置。链接的 IoT 中心可以在任何 Azure 区域中。可以将其他订阅中的中心链接到你的预配服务。

1. 在左侧导航区域的 **“设置”** 下，单击 **“证书”**。

    你可以在此管理 X.509 证书，该证书可通过 X.509 证书身份验证来保护 Azure IoT 中心的安全。你将在之后的实验室中研究 X.509 证书。

1. 在左侧导航区域的 **“设置”** 下，单击 **“管理注册”**。

    你可以在此管理注册组和单个注册。

    注册组可用于共享所需初始配置的大量设备，或者全部转到同一租户的设备。注册组是一组共享特定证明机制的设备。注册组同时支持 X.509 和对称。X.509 注册组中的所有设备都提供已由同一根或中间证书颁发机构 (CA) 签名的 X.509 证书。对称密钥注册组中的每个设备都提供派生自组对称密钥的 SAS 令牌。注册组名称和证书名称必须是小写的字母和数字，并可包含连字符。

    单个注册是针对可进行注册的单个设备的条目。单个注册可以使用 X.509 叶子证书或 SAS 令牌（来自物理或虚拟 TPM）作为证明机制。单个注册中的注册 ID 为小写的字母和数字，并可包含连字符。单个注册可能会指定所需 IoT 中心设备 ID。

1. 花一分钟时间查看 **“设置”** 选项下的其他菜单选项

   > **注释**：  本实验室练习仅用于介绍 IoT 中心设备预配服务，让你更加熟悉 UI，因此，如果你目前感到有些茫然，请不要担心。之后的课程将更详细地介绍 DPS。
