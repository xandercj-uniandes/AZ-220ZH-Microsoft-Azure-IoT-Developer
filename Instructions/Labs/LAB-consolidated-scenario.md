﻿# 合并方案

这是一个正在进行的文档，其中包含可帮助编辑的完整方案。

> **注释**：一旦将整个方案整合到各个实验中，将会删除此选项。

## LAB_AK_01

### 实验室场景

你是一家名为 Contoso 的一流美食奶酪公司的 Azure IoT 开发人员。Contoso 评估了 IoT 的商机，并得出结论，他们可以实现巨大的收益。他们根据评估结果选择了 Microsoft Azure IoT。

首先，你需要熟悉 Azure 工具。

#### 练习 1：探索 Azure 门户和仪表板

在开始使用 Azure IoT 服务之前，最好先熟悉 Azure 本身的工作方式。

虽然我们通常将 Azure 称为“云”，但实际上它是一个 Web 门户，旨在实现从单个网站访问 Azure 资源。所有 Azure 资源都可通过 Azure 门户访问。

#### 练习 2：创建一个 Azure 仪表板和资源组

在 Azure 门户上，仪表板用于显示资源的自定义视图。通过使用图块显示信息，图块可以进行排列和调整大小，以帮助你以有用的方式组织资源。你可以创建许多不同的仪表板，这些仪表板提供不同的视图并用于不同的目的。

放置在仪表板上的每个磁贴都会公开一个或多个资源。除了显示单个资源的数据的磁贴以外，你还可以为名为资源组的对象创建磁贴。

资源组是一个逻辑组，其中包含项目或应用程序的相关资源。资源组可以包括解决方案的所有资源，或仅包括要作为组进行管理的那些资源。你可以根据最适合所在组织的选项，决定如何将资源分配至资源组。通常，将共享相同生命周期的资源添加到同一资源组，以便你可以轻松地将它们作为一组进行部署、更新和删除。

在以下任务中，你将：

* 创建一个可在本课程中使用的自定义仪表板
* 创建资源组并将“资源组”图块添加到仪表板

## LAB_AK_02

### 实验室场景

你是为 Contoso（一家精制和分销美食奶酪的公司）工作的 Azure IoT 开发人员。你的任务是探索 Azure 和 Azure IoT 服务，这些服务将用于公司计划实施的 IoT 解决方案。你已熟悉 Azure 门户并为你的项目创建了资源组。现在，你需要开始调查 Azure IoT 服务。

#### 练习 1：用唯一名称命名资源

在整个课程中，你将创建资源。为了确保实验室间的一致性，并帮助你在使用完资源后整理资源，我们将为你提供你应该使用的名称。但是，这些资源中的许多都公开了可在 Web 上使用的服务，这意味着它们必须具有全局唯一名称。为此，你将使用唯一标识符，该标识符将添加到资源名称的末尾。让我们创建你的唯一 ID。

#### 练习 2：使用 Azure 门户创建 IoT 中心

Azure IoT 中心是一项完全托管的服务，可在 IoT 设备和 Azure 之间实现可靠、安全的双向通信。Azure IoT 中心服务提供以下内容：

* 与数十亿个 IoT 设备建立双向通信
* 有多种设备到云和云到设备通信选项，包括单向消息传递、文件传输和请求-答复方法。
* 内置声明性消息路由到其他 Azure 服务。
* 设备元数据和同步状态信息的可查询存储。
* 使用每个设备的安全密钥或 X.509 证书进行安全的通信和访问控制。
* 广泛监视设备连接性和设备标识管理事件。
* 适用于最受欢迎的语言和平台的 SDK 设备库。

你可以使用多种方法来创建 IoT 中心。例如，你可以使用 Azure 门户创建 IoT 中心资源，这是你将在任务中执行的操作。但是，你也可以编程方式创建 IoT 中心（和其他资源）。在本课程中，我们将研究可用于创建和管理 Azure 资源的其他方法，包括 Azure CLI 和 PowerShell。

#### 练习 3：检查 IoT 中心服务

正如我们已经指出的那样，IoT 中心是托管在云中的托管服务，充当中央消息中心，用于在你的 IoT 应用程序与其管理的设备之间进行双向通信。

IoT 中心的功能可帮助你生成可缩放的全功能 IoT 解决方案，例如管理制造业中使用的工业设备，跟踪医疗保健中的宝贵资产以及监控办公楼使用情况和其他更多场景。IoT 中心监视通过跟踪设备创建、设备故障和设备连接等事件，帮助你对解决方案的运行状况进行维护。

#### 练习 4：使用 Azure 门户创建设备预配服务

Azure IoT 中心设备预配服务是 IoT 中心的帮助程序服务，无需人工干预即可实现对适当 IoT 中心的零接触即时预配。设备预配服务提供以下内容：

* 零接触预配到单个 IoT 解决方案，而工厂没有硬编码 IoT 中心连接信息（初始设置）
* 跨多个中心的负载均衡设备
* 根据销售交易数据（多租户）将设备连接到其所有者的 IoT 解决方案
* 根据用例将设备连接到特定的 IoT 解决方案（解决方案隔离）
* 以最低的延迟将设备连接到 IoT 中心（地理分片）
* 根据设备的更改重新预配
* 滚动设备用于连接到 IoT 中心的密钥（不使用 X.509 证书进行连接时）

你可以使用多种方法来创建 IoT 中心设备预配服务的实例。例如，你可以使用 Azure 门户，这是你将在任务中执行的操作。但是，你也可以使用 Azure CLI 或 Azure 资源管理器模板创建 DPS 实例。

#### 练习 5：检查设备预配服务

IoT 中心设备预配服务是 IoT 中心的一项帮助程序服务，它支持对正确的 IoT 中心进行零接触即时预配，而无需人工干预，使客户能够以安全和可扩展的方式预配数百万台设备。

## LAB_AK_03

### 实验室场景

作为 Contoso 的开发人员之一，你知道在开始构建 Azure IoT 解决方案之前设置开发环境是重要的一步。你知道 Microsoft 提供了许多可用于开发和支持 IoT 解决方案的工具，并且应该对团队将使用哪些工具做出一些决策。你将准备一个工作环境，供团队用于在 Azure 云端和本地工作环境中开发你的 IoT 解决方案。

经过一番讨论，你的团队对开发环境做出了以下高层决策：

* 操作系统：Windows 10 将用作操作系统。大多数团队成员都使用 Windows，因此这是一个合理的选择。你注意到 Azure IoT 服务支持其他操作系统（如 Mac OS 和 Linux ）， Microsoft 为选择这些备选方案之一的团队成员提供支持文档。
* 一般编码工具：Visual Studio Code 和 Azure CLI 将作为主要的编码工具。这两种工具均支持利用 Azure IoT SDK 的 IoT 扩展。
* IoT Edge 工具：Docker 桌面社区和 Python 将用于支持自定义 IoT Edge 模块开发。

为了支持这些决定，你将设置以下环境：

* Windows 10 64 位：专业版、企业版或教育版（版本15063 或更新版本）。包括
  * 4GB – 8GB 系统 RAM（对于Docker，RAM 越高越好）
  * 必须启用 Windows 的 Hyper-V 和容器功能。
  * 必须在 BIOS 设置中启用 BIOS 级硬件虚拟化支持。

  > **注释**：在虚拟机上设置开发环境时，VM 环境必须支持嵌套虚拟化 - [嵌套虚拟化](https://docs.microsoft.com/zh-cn/virtualization/hyper-v-on-windows/user-guide/nested-virtualization)

* Azure CLI（当前/最新）
* .NET Core 3.0.100（或更高版本）SDK
* VS 代码（最新）
* Python 3.7（非 3.8）
* Docker Desktop Community 2.1.0.5（或更高版本）设置为 Linux 容器
* Power BI Desktop（用于数据可视化）
* VS Code 和 Azure CLI 的 IoT 扩展

> **注释**：为此课程创建了一个虚拟机，该虚拟机提供了上面指定的大多数工具。以下说明支持使用准备好的 VM 或使用 PC 在本地设置开发环境。

#### 练习 1：安装开发工具和产品

> **注释**：与本练习相关的工具和产品已预先安装在为此课程创建的虚拟机上。在继续之前，请咨询你的课程讲师，了解你是否要使用托管实验室 VM 环境完成实验，或者在电脑上本地设置开发环境。

#### 练习 2：安装开发工具扩展

Visual Studio Code 和 Azure CLI 工具均支持扩展，可帮助开发人员更有效地创建其解决方案。IoT 扩展由 Microsoft 开发，可利用 IoT SDK 并缩短开发时间。

#### 练习 3：设置课程实验室文件和替代工具

本课程中的许多实验室都依赖于预先构建的资源，例如可以用作实验室活动起点的代码项目。我们通过使用 GitHub 项目提供对这些实验室资源的访问。除了直接支持课程实验室的资源（GitHub 项目中包含的资源）之外，还有一些工具可用于支持实际课程之外的学习机会。下面的说明将引导你完成这两种资源类型的配置。

## LAB_AK_04

### 实验室场景

Contoso 以生产高质量的奶酪而闻名。由于公司的知名度和销售量都在迅速增长，他们希望采取措施来确保其奶酪保持其客户期望的高质量水平。

过去，温度和湿度数据是在每次轮班期间由工厂工人收集。该公司担心，随着新设施上线，工厂扩建将需要加强监控，而用于收集数据的手动流程将无法缩放。

Contoso 已决定启动使用 IoT 设备监控温度和湿度的自动化系统。遥测数据的通信速率将可调整，随着批量奶酪通过对环境敏感的处理流程，确保其制造过程受到控制。

为了在全面实施之前评估此资产监视解决方案，你需要将 IoT 设备（包括温度和湿度传感器）连接到 IoT 中心。

#### 练习 1：验证实验室先决条件

本实验室假定以下 Azure 资源可用：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |

#### 练习 2：使用 Azure CLI 创建 Azure IoT 中心设备 ID

`iot` Azure CLI 模块包括几个命令，用于在 `az iot hub device-identity` 命令组下管理 Azure IoT 中心内的 IoT 设备。这些命令可用于在脚本内或直接从命令行/终端管理 IoT 设备。

#### 练习 3：配置和测试模拟设备 (C#)

在本练习中，你将配置以 C# 编写的模拟设备，以使用在上一练习中创建的设备 ID 和共享访问密钥连接到 Azure IoT 中心。然后，你将测试设备并确保 IoT 中心按预期从设备接收遥测。

## LAB_AK_05

### 实验室场景

Contoso 管理层正在推动更新其资产监视和跟踪解决方案，该解决方案将使用 IoT 设备来减少当前系统下所需的手动数据输入工作，并在传送过程中提供更高级的监视。该解决方案依赖于预配和取消预配 IoT 设备的能力。管理预配要求的最佳选择为 DSP。

建议的系统将使用具有集成传感器的 IoT 设备来跟踪运输过程中运输容器的位置、温度、压力。这些设备将放置在 Contoso 用于运输奶酪的现有运输容器中，并将使用车辆提供的 WiFi 连接到 Azure IoT 中心。新系统将提供对产品环境的连续监视，并在检测到问题时启用各种通知方案。

在 Contoso 的奶酪包装设施中，当一个空容器进入系统时，它将配备新的 IoT 设备，然后装载包装好的奶酪产品。需要使用设备预配服务将 IoT 设备自动预配到 IoT 中心。当集装箱到达目的地时，将检索 IoT 设备，然后通过 DPS“解除授权”。该设备将重新用于以后的运输。

你的任务是使用 DPS 验证设备预配和取消预配过程。在流程的初始阶段，将使用“单个注册”方法。

#### 练习 1：验证实验室先决条件

本实验室假定以下 Azure 资源可用：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| 设备预配服务 | AZ-220-DPS-_{YOUR-ID}_ |

#### 练习 2：在 DPS 中创建新的单个注册（对称密钥）

在本练习中，将使用_对称密钥证明_在设备预配服务 (DPS) 中为设备创建新的单个注册。

#### 练习 3：配置模拟设备

在本练习中，你将配置用 C＃写入的模拟设备，并使用在上一个单元中创建的单独注册连接到 Azure IoT。还要将代码添加到模拟设备中，才能基于 Azure IoT 中心内的设备孪生来读取和更新设备配置。

在本练习中创建的模拟设备代表将要放置于装运箱/包装盒中，并用于监视运输过程中 Contoso 产品情况的 IoT 设备。从设备发送到 Azure IoT 中心的传感器遥测数据包括容器的温度、湿度、压力和纬度/经度坐标。该设备是整体资产跟踪解决方案的一部分。

这与之前模拟设备连接到 Azure 的实验室不同，因为在该实验室中，你使用共享访问密钥进行身份验证，这种方式尽管无需进行设备预配，但也没有预配管理的优势（例如设备孪生），而且还要对共享密钥进行大范围分配和管理。  在本实验室中，你将通过设备预配服务来预配唯一的设备。

#### 练习 4：测试模拟设备

在本练习中，你将运行模拟设备并验证其是否在向 Azure IoT 中心发送传感器遥测。你还将通过更新 Azure IoT 中心内部模拟设备的设备孪生来更新将遥测发送到 Azure IoT 中心的延迟。

#### 练习 5：停用设备

在本单元中，你将执行从设备预配服务 (DPS) 和 Azure IoT 中心停用设备所需的任务。要从 Azure IoT 解决方案中完全停用 IoT 设备，必须将其从这两项服务中删除。当运输箱到达其最终目的地时，传感器将从运输箱中取出，并且需要“解除授权”。彻底停用设备是 IoT 解决方案中 IoT 设备生命周期中的重要一步。

## LAB_AK_06

### 实验室场景

你目前在 Contoso 的资产监视和跟踪解决方案上所做的工作使你能够使用个人注册验证设备预配和取消预配流程。管理团队现在要求你开始大规模实实现该流程。

要使项目继续进行，你需要证明设备预配服务可用于使用 X.509 证书身份验证自动安全地注册更多设备。

#### 练习 1：验证实验室先决条件

本实验室假定以下 Azure 资源可用：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| 设备预配服务 | AZ-220-DPS-_{YOUR-ID}_ |

#### 练习 2：使用 OpenSSL 生成和配置 X.509 CA 证书

在本练习中，你将在 Azure Cloud Shell 中使用 OpenSSL 生成 X.509 CA 证书。此证书将用于在设备预配服务 (DPS) 中配置组注册。

#### 练习 3：在 DPS 中创建组注册（X.509 证书）

在本练习中，你将使用_证书证明_方法在设备预配服务 (DPS) 中为设备创建新的个人注册。

#### 练习 4：使用 X.509 证书配置模拟设备

在本练习中，你将配置用 C# 编写的模拟设备，以使用 X.509 证书通过设备预配服务 (DPS) 连接到 Azure IoT 中心。本练习还将向你介绍 `/LabFiles` 目录中 **“模拟设备”** 源代码中的工作流，以及如何通过 DPS 进行身份验证并将消息发送到 IoT 中心。

#### 练习 5：处理设备孪生必需属性的更改

在本练习中，你将修改模拟设备的源代码，以包括一个事件处理程序，根据从 Azure IoT 中心发送到设备的设备孪生所需属性更改以更新设备配置。

设备孪生是存储设备状态信息（包括元数据、配置和条件）的 JSON 文档。Azure IoT 中心为你连接到 IoT 中心的每个设备维护一个设备孪生。

设备预配服务 (DPS) 包含使用组注册所注册设备的初始设备孪生所需属性。设备注册后，将使用 DPS 的初始设备孪生配置在 IoT 中心内进行创建。注册后，Azure IoT 中心为 IoT 中心设备注册表中的每个设备维护一个设备孪生（及其属性）。

当为 Azure IoT 中心内的设备更新设备孪生所需属性时，所需更改将使用 C# SDK 的 `DesiredPropertyUpdateCallback` 事件发送到 IoT 设备。通过在设备代码中处理此事件，可以通过轻松管理 Azure IoT 中心内设备的设备孪生状态来根据需要更新设备配置和属性。

这套步骤与早期实验中使用模拟设备的步骤非常相似，因为概念和过程是相同的。  预配设备后，用于验证预配过程的方法不会更改设备孪生属性更改的处理方式。

#### 练习 6：测试模拟设备

在本练习中，你将运行模拟设备。首次启动设备时，它将连接到设备预配服务 (DPS)，并使用配置的组注册自动注册。注册 DPS 组注册后，设备将自动在 Azure IoT 中心设备注册表中注册。注册并登记后，设备将开始使用配置的 X.509 证书身份验证与 Azure IoT 中心安全通信。

#### 练习 7：淘汰组注册

在本练习中，你将从设备预配服务和 Azure IoT 中心淘汰注册组及其设备。

## LAB_AK_07

### 实验室场景

Contoso Management 对自动设备注册的实施印象深刻，现已准备好探索能够提供业务价值的方案。

奶酪制造业务的关键部分是将奶酪打包并运输给客户。为了最大程度地提高成本效率，Contoso 运营了一个本地包装设备。工作流非常简单 - 将包裹组装起来以备运输，然后将其放置在传送带上，传送带会将包裹运送至邮寄箱。成功的衡量指标是离开传送带的包裹数量。

传送带是你流程中的关键环节，并会受到振动监控。传送带配备三种速度：停止、慢速和快速。以慢速交付的包裹数量少于以较快速度交付的包裹数量，但以较慢速度交付的振动也相应较小。如果振动过大，则必须停止并检查传送带。

有不同的区域类型。强制振动是由外力引起的振动。例如，车轮断裂或未正确放置在传送带上的重磅包裹等力。也会出现振动不断增加的情况，如果超出设计限制，可能会发生这种情况。

振动通常以加速度来衡量（米/二次方秒，m/s²）。

这里的最终目标是执行预防性维护。在造成任何损坏之前，请先检测问题出在什么地方。 

> **注释**：**预防性维护**（有时称为预防性维护）是一种设备维护程序，用于计划在设备正常运行时执行的维护活动。这种方法的目的是避免意外故障，这些故障通常会导致代价高昂的设备中断。

检测异常振动水平并不总是那么容易。因此，你正在寻求 Azure IoT 中心来检测数据异常。你计划在传送带上安装一个振动检测传感器，以将连续遥测发送到 IoT 中心。IoT 中心将使用 Azure 流分析和内置的机器学习 (ML) 模型向你发出振动异常的预警。你还计划归档所有遥测数据，以防万一需要。

你决定首先使用模拟遥测来构建计划系统的原型。

#### 练习 1：验证实验室先决条件

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| 设备 ID | VibrationSensorId |

#### 练习 2：编写振动遥测代码

监控传送带的关键是振动遥测的输出。振动通常以加速度 (m /s²) 表示，尽管有时以 g 力表示，其中1 g = 9.81 m/s²。有三种振动类型。

* 自然振动，即结构振动的频率。
* 当结构受到冲击时会发生自由振动，但随后即便不受干扰也会一直保持振动。
* 当结构处于一定应力下时会发生的强制振动。

受迫振动对我们的传送带而言是一个危险。即使最初的程度很弱，但这种振动会积累，最终导致结构过早失效。传送带操作中的自由振动很少。众所周知，大多数机器都有自然振动。

你将构建的代码示例将模拟传送带以一定速度（停止、慢速、快速）运行。传送带运行得越快，运送的包裹越多，但是振动的影响越大。我们将基于具有一定随机性的正弦波添加自然振动。我们的异常情况检测系统可能会错误地将此正弦波中的尖峰或下降识别为异常。然后，我们将添加两种形式的强制振动。第一，具有振动循环增加的效果（请参见下图）。第二，振动增加，增加了一个额外的正弦波，开始时振动较小但一直在增加。

我们假设传送带只有一个传感器设备（我们的模拟 IoT 设备）。除了传递振动数据外，传感器还可以抽出一些其他数据（已交付的包裹、环境温度和类似指标）。在本实验中，其他值将发送到存储档案。

在本练习中，本实验中几乎所有的编码都将完成。你将使用 Visual Studio Code 以 C# 生成模拟器代码。

在本练习中，你将：

* 生成传送带模拟器
* 将遥测消息发送到上一个单元中创建的 IoT 中心

在本实验室的后面部分，你将完成少量的 SQL 编码。

#### 练习 3：创建到 Azure Blob 存储的消息路由

我们的振动监控系统的体系结构要求将数据发送到两个目的地：存储和分析。Azure IoT 提供了一种通过*消息路由选择*将数据定向到正确服务的好方法。

在我们的场景中，我们需要创建两个路由：

* 第一个路由是存储以存档数据
* 第二个路由是传输至事件中心进行异常情况检测

由于最好一次性生成并测试一条消息路由，因此本练习将重点介绍存储路由。我们将此路由称为“日志记录”路由，其中涉及深入研究创建 Azure 资源的几个级别。Azure 门户中提供了生成此路由所需的所有功能。

我们将使存储路由保持简单，并使用 Azure Blob 存储（不过也可以使用 Data Lake Storage）。消息路由的主要功能是过滤传入数据。仅当满足特定条件时，以 SQL 编写的筛选器才会向下输出路由。

筛选数据的最简单方法之一是根据消息属性筛选，这就是我们在代码中添加了这两行的原因：

```csharp
...
telemetryMessage.Properties.Add("sensorID", "VSTel");
...
loggingMessage.Properties.Add("sensorID", "VSLog");
```

嵌入到我们的消息路由中的 SQL 查询可以测试 `sensorID` 值。

在本练习中，你将创建并测试日志记录路由。

#### 练习 4：日志记录路由 Azure 流分析作业

为了验证日志记录路由是否按预期工作，我们将创建一个流分析作业，将日志记录消息路由到 Blob 存储，然后可以使用 Azure 门户中的存储资源管理器对其进行验证。

这将使我们能够验证我们的路由是否包括以下设置：

* **名称** - 振动日志记录路由
* **数据源** - 设备消息
* **路由查询** - sensorID = "VSLog"
* **终结点** - 振动记录终结点
* **已启用** - true

> **注释**：将数据路由到存储，然后再次通过 Azure 流分析将其发送到存储似乎很奇怪。  在生产场景中，这两条路径不会长期存在。  相反，不会有我们在此处创建的第二个路径。  我们仅仅将其作为一种在实验室环境中以易于验证的方式演示 Azure 流分析的一种方式。

## LAB_AK_08

### 实验室场景

你已经开发了一种设备模拟器，用于为传送带系统生成振动数据和其他遥测输出，该系统可接收包裹并将其运输至邮寄箱中。你已经生成并测试了将数据发送到 Azure Blob 存储的日志记录路由。

第二个路由将是事件中心，因为事件中心是流分析的便捷输入。流分析是处理异常情况检测的便捷方法，例如我们在场景中寻找的过度振动。

将为 IoT 中心创建此路由，然后将其添加为 Azure 流分析作业的输入。

我们需要更新作业以处理两个输入和两个输出，以及一个更复杂的查询。

创建第二个路由的过程与第一个路由类似，尽管在创建终结点时有所不同。选择事件中心作为遥测路由的终结点。

在本练习中，你将创建一个事件中心*命名空间*。然后，你必须创建一个命名空间的*实例*以完成事件中心的设置。然后，你可以将此实例用作新消息路由的目标。

创建路由后，我们将继续更新查询。

#### 调用内置的机器学习模型

我们要调用的内置机器学习 (ML) 函数是 `AnomalyDetection_SpikeAndDip`。

`AnomalyDetection_SpikeAndDip` 函数会获取数据的滑动窗口，并检查是否存在异常。滑动窗口可以是最近两分钟的遥测数据。该滑动窗口可以近乎实时地同遥测流保持同步。如果滑动窗口的尺寸增加，则异常情况检测的准确度通常也会增加。延迟也一样。

随着数据流的继续，该算法将建立一个正常值范围，然后将新值与这些正常值进行比较。结果是每个值的百分比得分，用于确定给定值为异常的置信度。低置信度会被忽略，问题是什么百分比置信度的值可以接受？在我们的查询中，计划将该临界点设置为 95%。

总会有复杂状况出现，例如存在数据空白（可能是传送带停止运转片刻）。算法通过插补数值来处理数据空白。

> **注释**：在统计学中，插补是用替换值替换缺失数据的过程。关于插补的更多信息，请点击[这里](https://en.wikipedia.org/wiki/Imputation_%28statistics%29)。

遥测数据的急剧上升和下降一种暂时性的异常。但是，由于我们正在处理正弦波的振动，因此可以预期，一小段“正常”值之后会出现较高值或较低值，从而触发异常警报。操作员正在寻找在短时间内出现的异常群集 。这种群集表明出现了异常状况。

还存在其他内置 ML 模型，例如趋势检测模型。在本模块中我们不探讨这些模型，但我们鼓励学生做进一步研究。

#### 使用 Power BI 实现数据的可视化效果

直观呈现数字数据（尤其是大量数据）本身就是一个难题。我们该如何向操作人员发出异常序列（可推断出有问题出现）的警报？

我们在此模块中使用的解决方案是使用 Power BI 的某些内置功能，以及 Azure 流分析中以 Power BI 可以引入的实时格式发送数据的功能。

我们使用 Power BI 的仪表板功能来创建大量磁贴。一个磁贴包含实际的振动测量值。另一个磁贴是一个仪表，显示对异常值（从 0.0 到 1.0 ）的置信度。第三个磁贴指示置信度是否达到 95％。最后，第四个磁贴显示在过去一小时内检测到的异常数。通过将时间作为 x 轴，此磁贴可以清晰地显示出是否在短时间内连续检测到多个异常值，原因是这些异常值会在水平方向上聚集在一起。

第四个磁贴使你能够将异常值与遥测控制台窗口中的红色文本进行比较。当强制施加震动或者震动不断增加，又或者二者同时发生时，是否能够检测到异常现象？

我们将创建事件中心，创建第二条路由，更新 SQL 查询，创建 Power BI 仪表板，然后全部运行！

#### 练习 1：注册 PowerBI

Power BI 可用作个人数据分析和可视化工具，也可用作小组项目、部门或整个公司的分析和决策引擎。在本实验室后面的部分中，将生成仪表板并使用 PowerBI 直观呈现数据。本练习说明了如何以个人身份注册 Power BI。

>**注：**如果已拥有 PowerBI 订阅，则可跳至下一步。

#### 练习 2：验证实验室先决条件

为了在仪表板上可视化数据，我们需要一些实时遥测。在本练习中，你将确保上一个实验中的设备模拟器应用正在运行。

#### 练习 3：添加 Azure 事件中心路由和异常查询

现在，我们已将遥测数据流传输到 IoT 中心，我们将向我们的解决方案中添加一个 Azure 事件中心命名空间和 Azure 事件中心实例。Azure 事件中心适合处理流数据，并支持实时仪表板方案 - 非常有利于将振动数据传递到 Power BI。

#### 练习 4：创建实时消息路由

现在我们有一个事件中心命名空间和一个事件中心，我们需要将遥测数据从 IoT 中心传递到事件中心。

#### 练习 5：添加遥测路由

添加此全新 IoT 中心路由，并将遥测数据流式传输到事件中心后，我们需要更新流分析作业。此作业需要使用来自事件中心的数据，并使用 **AnomalyDetection_SpikeAndDip** ML模型执行分析，然后将结果输出到 Power BI。

#### 练习 6：创建 Power BI 仪表板

现在进行方案的最终部分 - 数据可视化的实际过程。我们已经更新了作业，以通过 ML 模型处理振动遥测并将结果输出到 Power BI。在 Power BI 中，我们需要创建一个包含许多磁贴的仪表板，用来将结果可视化并为操作员提供决策支持。

## LAB_AK_09

### 实验室场景

Contoso 正在安装新的连接的恒温器，以便能够监控不同奶酪储藏室的温度。你将创建一个警报，以在创建新的恒温器时通知设施管理员。

要创建警报，你需要在 IoT 中心新建恒温器时将由设备创建的事件类型推送到事件网格。你将拥有一个逻辑应用实例，该实例将对此事件做出响应（在事件网格上），并将发送电子邮件以提醒设施管理员已创建新设备、设备 ID 和连接状态。

#### 练习 1：验证实验室先决条件

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |

如果资源不可用，请在实验室开始之前执行 **lab-setup.azcli** 脚本。

#### 练习 2：创建发送电子邮件的 HTTP Webhook 逻辑应用

Azure 逻辑应用是一种云服务，可在需要跨企业或组织集成应用、数据、系统和服务时帮助你对任务、业务流程和工作流程进行计划、自动化和编排。

在本练习中，你将新建一个通过 HTTP Webhook 触发的 Azure 逻辑应用，然后使用 Outlook.com 电子邮件地址发送电子邮件。

#### 练习 3：配置 Azure IoT 中心事件订阅

Azure IoT 中心与 Azure 事件网格集成在一起，因此你可以将事件通知发送到其他服务并触发下游流程。你可以将业务应用程序配置为侦听 IoT 中心事件，以便以可靠、可缩放和安全的方式对关键事件做出反应。例如，生成一个可更新数据库，创建工单，并在新 IoT 设备注册到 IoT 中心时发送电子邮件通知的应用程序。

在本练习中，你将在 Azure IoT 中心内创建事件订阅以设置事件网格集成，用来触发逻辑应用发送警报电子邮件。

## LAB_AK_10

### 实验室场景

Contoso 的资产状况跟踪显示了特定资产的温度峰值，我们希望找到根本原因。我们想了解发生了什么：我们将来自运输卡车和飞机传感器的 IoT 设备的传感器数据关联起来。其中一辆卡车的温度上升，并在其中一个装有带温度和湿度传感器的 IoT 设备的运输箱中产生了热量峰值。你的团队将需要能够近乎实时地浏览数据并进行根本原因分析，以帮助改进交付流程，确保产品保持最佳状态。

你将在解决方案中添加时序见解，以快速存储、可视化和查询大量时序数据，这些数据是由卡车、飞机和运输箱中的 IoT 设备生成的，以便可视化随时间的变化。

#### 练习 1：验证实验室先决条件

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | `AZ-220-RG` |
| IoT 中心 | `AZ-220-HUB-{YOUR-ID}` |
| 设备 ID | `TruckDevice` |
| 设备 ID | `AirplaneDevice` |
| 设备 ID | `ContainerDevice` |

#### 练习 2：设置时序见解

Azure 时序见解 (TSI) 是一种端到端平台即服务 (PaaS) 产品，用于大规模收集、处理、存储、分析和查询来自物联网 (IoT) 解决方案的数据。TSI 专为临时数据资源管理以及针对时序进行了高度语境化和优化的数据的操作分析而设计。

在本练习中，你将设置时序见解 (TSI) 与 Azure IoT 中心的集成。

#### 练习 3：运行模拟 IoT 设备

在本练习中，你将运行模拟的设备，以便它们开始将遥测事件发送到 Azure IoT 中心。

#### 练习 4：查看 Azure 时序见解资源管理器

本练习将向你介绍如何使用时序见解 (TSI) 资源管理器处理时序数据。

## LAB_AK_11

### 实验室场景

Contoso 在全球各地拥有奶酪生产工厂。工厂配备生产线，有多台机器用于制作奶酪。目前，他们已将 IoT 设备连接到每台计算机，这些设备将传感器数据流式传输到 Azure 并处理云中的所有数据。由于正在收集大量数据，而且某些计算机需要紧急时间响应，因此 Contoso 希望添加一个网关设备，将用于处理数据的尖端智能仅用于向云发送重要的数据。另外，即使本地网络很差，也能快速处理数据和作出反应。

你将设置一个新的 IoT Edge 设备，该设备可以监视其中一台计算机的温度，并部署流分析模块以计算平均温度，并向该设备发送警报以便迅速采取行动。

#### 练习 1：验证实验室先决条件

[待定]

#### 练习 2：部署启用 Azure IoT Edge 的 Linux VM

在本练习中，将从 Azure 市场部署具有 Azure IoT Edge 运行时支持的 Ubuntu Server VM。

#### 练习 3：使用 Azure CLI 在 IoT 中心中创建 IoT Edge 设备标识

在本练习中，你将使用 Azure CLI 在 Azure IoT 中心内创建新的 IoT Edge 设备标识。

#### 练习 4：将 IoT Edge 设备连接到 IoT 中心

在本练习中，你将把 IoT Edge 设备连接到 Azure IoT 中心。

#### 练习 5：将 Edge 模块添加到 Edge 设备

在本练习中，你将添加模拟温度传感器作为自定义 IoT Edge 模块，并将其部署在 IoT Edge 设备上运行。

#### 练习 6：将 Azure 流分析部署为 IoT Edge 模块

现在，tempSensor 模块已部署并在 IoT Edge 设备上运行，我们可以添加一个流分析模块，该模块可以在将消息发送到 IoT 中心之前处理 IoT Edge 设备上的消息。

## LAB_AK_12

### 实验室场景

本实验室是理论性实验室，将带你逐步了解如何将 IoT Edge 设备用作网关。

将 IoT Edge 设备用作网关有三种模式：透明、协议转换和标识转换：

**透明** - 理论上可以连接到 IoT 中心的设备可以改为连接到网关设备。下游设备有其自己的 IoT 中心标识，并将使用任一 MQTT、AMQP 或 HTTP 协议。网关只是在设备与 IoT 中心之间传递通信。这些设备不知道它们正在通过网关与云进行通信，通过 IoT 中心与设备交互的用户觉察不到中间网关设备。因此，网关是透明的。请参阅“创建透明网关”，了解有关将 IoT Edge 设备用作透明网关的详细信息。

**协议转换** - 也称为不透明网关模式，某些不支持 MQTT、AMQP 或 HTTP 的设备可以使用网关设备以这些设备的名义向 IoT 中心发送数据。网关能够理解下游设备使用的协议，是 IoT 中心唯一具有标识的设备。所有信息看起来像来自同一台设备，即网关。如果云应用程序想要以设备为单位分析数据，则下游设备就必须在其消息中嵌入额外的标识信息。此外，IoT 中心基元（例如孪生和方法）仅适用于网关设备，而不适用于下游设备。

**标识转换** - 无法连接到 IoT 中心的设备可以改为连接到网关设备。网关代表下游设备提供 IoT 中心标识和协议转换。网关非常智能，它能够理解下游设备使用的协议，为其提供标识，并转换 IoT 中心基元。下游设备作为一流设备出现在 IoT 中心，随附孪生和方法。用户可以与 IoT 中心的设备进行交互，但并觉察不到中间网关设备。

#### 练习 1：验证实验室先决条件

[待定]

#### 练习 2：部署启用 Azure IoT Edge 的 Linux VM

在本练习中，将从 Azure 市场部署具有 Azure IoT Edge 运行时支持的 Ubuntu Server VM。

#### 练习 3：生成和配置 IoT Edge 设备 CA 证书

在本练习中，将使用 Linux 生成测试证书。你将使用 `Azure/IoTEdge` GitHub 项目中包含的帮助程序脚本在 `AZ-220-VM-EDGEGW-{YOUR-ID}` 虚拟机上执行此操作。

#### 练习 4：使用 Azure 门户在 IoT 中心中创建 IoT Edge 设备标识

在本练习中，你将在 Azure IoT 中心为 IoT Edge 透明网关创建一个新的 IoT Edge 设备标识。

#### 练习 5：设置 IoT Edge 网关主机名

在本练习中，你将为 **AZ-220-VM-EDGEGW-_{YOUR-ID}_** 的“公共 IP 地址”配置 DNS 名称，然后将该 DNS 名称配置为 IoT Edge 网关设备的 `hostname`。

#### 练习 6：将 IoT Edge 网关设备连接到 IoT 中心

在本练习中，你将把 IoT Edge 设备连接到 Azure IoT 中心。

#### 练习 7：打开 IoT Edge 网关设备端口进行通信

在本练习中，将配置网络安全组 (NSG)，以确保从 Internet 访问 Azure IoT Edge 网关的安全。需要打开用于 MQTT、AMQP 和 HTTPS 通信的必要端口，以便下游 IoT 设备可以与网关通信。

为使 Azure IoT Edge 网关正常运行，必须打开至少一个受 IoT Edge 中心支持的协议以接收来自下游设备的入站流量。受支持的协议为 MQTT、AMQP 和 HTTPS。

受 Azure IoT Edge 支持的 IoT 通信协议具有以下端口映射：

| 协议 | 端口号 |
| --- | --- |
| MQTT | 8883 |
| AMQP | 5671 |
| HTTPS<br/>MQTT + WS (Websocket)<br/>AMQP + WS (Websocket) | 443 |

为设备选择的 IoT 通信协议需要为防火墙打开相应的端口，以保护 IoT Edge 网关设备的安全。在此实验室中，将使用 Azure 网络安全组 (NSG) 来保护 IoT Edge 网关的安全，因此将在这些端口上打开 NSG 的入站安全规则。

在生产方案中，你只希望打开最小数量的端口以供设备进行通信。如果使用的是 MQTT，则仅打开端口 8883 进行入站通信。打开其他端口将引入攻击者可利用的其他安全攻击途径。最好的安全做法是仅打开解决方案所需的最小端口数。

#### 练习 8：在 IoT 中心中创建下游设备标识

在本练习中，将在 Azure IoT 中心为下游 IoT 设备创建一个新的 IoT 设备标识。将配置此设备标识，以便 Azure IoT Edge 网关成为此下游设备的父设备。

#### 练习 9：将下游设备连接到 IoT Edge 网关

在本练习中，将配置预生成的下游设备以连接到 IoT Edge 网关。

#### 练习 10：验证事件流

在本练习中，将使用 Azure CLI 监视通过 IoT Edge 网关从下游 IoT 设备发送到 Azure IoT 中心的事件。这将验证一切是否正常运行。

## LAB_AK_13

### 实验室场景

Contoso 的仓库将准备打包的库存转移到传送带上。

为了确保包装了正确数量的产品，你将添加一个简单的模块来对同一 IoT Edge 设备上另一物体检测模块（模拟）在传送带上检测到的物体进行计数。我们将展示如何创建一个执行对象计数的自定义模块。

本实验室包括开发机器的以下先决条件（实验室主机环境- VM 或 PC）：

* 安装了以下扩展的 Visual Studio Code：
  * Microsoft 的 [Azure IoT Tools](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.azure-iot-tools) 
  * Microsoft [C#](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)
  * [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
* 在 Docker 客户端版本 18.03.0 或更高版本的开发机器上安装了 Docker Community Edition
  * [下载适用于 Mac 和 Windows 的 Docker 桌面](https://www.docker.com/products/docker-desktop)

    > **重要事项**：由于 2020 年 1 月 13 日取消了低于 TLS 版本 1.2 的 TLS 对 Azure 容器注册表的支持，因此你必须使用 Docker 客户端 18.03.0 或更高版本。

#### 练习 1：验证实验室先决条件

[待定]

#### 练习 2：安装 Azure IoT EdgeHub 开发工具

在本练习中，你将安装 Azure IoT EdgeHub 开发工具。

#### 练习 3：创建 Azure 容器注册表

Azure 容器注册表为容器部署提供专用  Docker 图像的存储。Azure 容器注册表服务是基于开放源代码 Docker 注册表 2.0 管理，专用 Docker 的注册表服务。Azure 容器注册表用以存储和管理你的专用 Docker 容器图像。

在本练习中，你将使用 Azure 门户创建新的 Azure 容器注册表资源。

#### 练习 4：在 C\# 中创建自定义 Edge 模块

在本练习中，你将创建一个 Azure IoT Edge 解决方案，其中包含用 C# 编写的自定义 Azure IoT Edge 模块。

#### 练习 5：使用 IoT Edge 模拟器在附加模式下进行调试

在本练习中，你将使用 Visual Studio Code 中的 IoT Edge 模拟器构建和运行自定义 IoT Edge 模块解决方案。

#### 练习 6：部署 IoT Edge 解决方案

在本练习中，你将构建自定义 IoT Edge 模块并将其发布到 Azure 容器注册表 (ACR) 服务中。一旦发布到 ACR，自定义模块将可用于部署到任何 IoT Edge 设备。

## LAB_AK_14

### 实验室场景

传送带系统监视振动、遥测并计数对象。我们希望我们的系统能够抵御网络中断，并且还可以优化一天中特定时间的遥测数据的批量上传（负载均衡网络使用率）。我们将配置 IoT Edge，以在网络中断时支持脱机运行，并且我们将了解本地存储传感器遥测，并配置在给定时间定期同步。

你将学习 IoT Edge 设备位于企业网络上（需要代理设置）或需要扩展的脱机功能的不同方案。

#### 练习 1：验证实验室先决条件

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| IoT 设备 | SimulatedThermostat |

#### 练习 2：部署启用 Azure IoT Edge 的 Linux VM

在本单元中，你将部署来自 Azure 市场的具有 Azure IoT Edge 运行时支持的 Ubuntu Server VM。在以前的实验室中，你已经使用 Azure 门户创建了 VM。这次，我们将使用 Azure CLI 创建 VM。

#### 练习 3：使用子级 IoT 设备设置 IoT Edge 父级

在本练习中，你将在 Azure IoT 中心内注册 IoT Edge 设备，并在子关系中配置 IoT 设备。这将使方案能够在与云中的 Azure IoT 中心通信之前，通过 IoT Edge 设备作为网关向子 IoT 设备发送消息。

使用父 / 子关系，包括 IoT Edge 网关（父级）和其他 IoT 设备（子或叶设备），可以在 Azure IoT 解决方案中使用脱机功能。

下图显示了作为父级设备的 Azure IoT Edge 设备与子级设备之间的关系：

![IoT Edge 父级与子级设备图](images/IoTEdge-Parent-Child-Relationship.jpg "IoT Edge Parent with Child Device Diagram")

在这种情况下，子设备使用其 Azure IoT 中心凭据连接到父级 IoT Edge 设备并对其进行身份验证。身份验证后，子级 IoT 设备将消息发送到 IoT Edge 设备上的 Edge 中心 (`$edgeHub`) 。一旦消息到达父级 IoT Edge 设备，则 IoT Edge 模块和路由将按配置处理消息；包括在连接后将消息发送到 Azure IoT 中心。

当父级 IoT Edge 设备断开连接（或断开与 Azure IoT 中心的连接）时，它将自动将所有设备消息存储到 IoT Edge 设备。恢复连接后，IoT Edge 设备将恢复连接并将所有存储的消息发送到 Azure IoT 中心。根据设备的生存时间 (TTL) 配置，存储在 IoT Edge 设备上的消息可能会过期；默认情况下，该消息最多可存储 `7200` 秒（两个小时）。

#### 练习 4：将 IoT Edge 设备配置为网关

在本练习中，你将在先前创建的 Ubuntu 虚拟机上将 Azure IoT Edge 配置为 IoT Edge 透明网关设备。该配置将通过帮助程序脚本进行处理，该脚本是本单元的一部分，以使过程更快。

#### 练习 5：使用 Azure CLI 打开 IoT Edge 网关设备入站端口

在本练习中，将使用 Azure CLI 配置网络安全组 (NSG)，以确保从 internet 访问 Azure IoT Edge 网关的安全性。需要打开用于 MQTT、AMQP 和 HTTPS 通信的必要端口，以便下游 IoT 设备可以与网关通信。

为了使 Azure IoT Edge 网关与子 IoT 设备能够进行通信，必须打开设备协议的 TCP/IP 端口以用 **于入站** 通讯。该设备可以使用三种支持的协议之一与 IoT 网关通信。

以下是受支持协议的 TCP/IP 端口号：

| 协议 | 端口号 |
| --- | --- |
| MQTT | 8883 |
| AMQP | 5671 |
| HTTPS<br/>MQTT + WS (Websocket)<br/>AMQP + WS (Websocket) | 443 |

#### 练习 6：配置 IoT Edge 设备的生存时间和消息存储

在本练习中，你将在 Azure IoT Edge 网关设备上将 Edge 中心模块的消息生存时间 (TTL) 配置为比默认值长。你还将在 IoT Edge 设备上配置要存储消息的位置。

默认值 `7200` （2 小时）对于可能需要在离线模式下长时间运行的设备或解决方案来说不够长。为了使设备和解决方案能够在更长的断开连接时间内运行，你需要将 IoT Edge 中心模块的生存时间 (TTL) 属性配置为 1,209,600 秒，为期 2 周的 TTL。

IoT Edge 中心的模块孪生称为 `$edgeHub`，用于协调设备上运行的 IoT Edge中心与 Azure IoT 中心服务之间的通信。在模块孪生的所需属性中， `storeAndForwardConfiguration.timeToLiveSecs` 属性会以秒为单位指定当处于与路由终结点断开的状态时，例如 Azure IoT 中心，IoT Edge 中心能够保留消息的时间。

可以在特定设备上的部署清单中将 Edge 中心的 `timeToLiveSecs` 属性指定为单设备或大规模部署的一部分。在本单元中，你将使用 Azure IoT 中心的 Azure 门户用户界面来修改单个 IoT Edge 网关设备上的 Edge Hub (`$edgeHub`) 模块的 `timeToLiveSecs` 属性。

#### 练习 7：将子级 IoT 设备连接到 IoT Edge 网关

在本练习中，你将配置下游子 IoT 设备以使用其配置的对称密钥连接到 IoT 中心。设备将配置为使用包含对称密钥的连接字符串连接到 IoT 中心和父级 IoT Edge 设备；以及父级 IoT Edge 设备的网关主机名。

使用对称密钥向 IoT 中心对常规 IoT 设备进行身份验证的过程也适用于下游（或子级/叶）设备。唯一的区别是，你需要添加一个指向网关设备的指针来路由连接，或者在离线情况下，代表 IoT 中心处理身份验证。

在上一个单元中，你在 Azure IoT 中心创建了 IoT 设备标识。你复制了 **连接字符串** 用于 IoT 设备。或者，可以使用 Azure 门户访问连接字符串，以获取 Azure IoT 中心内设备的设备 ID。

#### 练习 8：测试设备连接性和脱机支持

在本练习中，你将监控 **ChildIoTDevice** 通过 **IoTEdgeGateway** IoT Edge 透明网关发送到 Azure IoT 中心的事件。然后，你将中断 **IoTEdgeGateway** 和 Azure IoT 中心之间的连接，以查看仍从子 IoT 设备发送到 IoT Edge 网关的遥测。之后，你将恢复与 Azure IoT 中心的连接，并监视 IoT Edge 网关继续将遥测发送到 Azure IoT 中心。

## LAB_AK_15

### 实验室场景

假设你在南方某地经营一家美味奶酪公司。该公司以其奶酪为荣，并非常小心地保持适用于老化奶酪的天然储藏室的完美温度和湿度。储藏室中有传感器用于报告温度和湿度。远程操作员可以根据需要将风扇设为新的设置，以保持适用于老化奶酪的理想环境。风扇可以加热和冷却，以及加湿和除湿。

储藏室用于使奶酪成熟，其恒定的温度、湿度和气流使其成为该过程的理想选择。更不用说让奶酪产品在天然储藏室中变成熟这本身是一个优良标志，而不是在一个人造地窖。在产品标签上包含某些内容！

可接受的老化奶酪的理想温度为 50 华氏度（10 摄氏度），可接受的最高温度为 5 度（2.78 摄氏度）。湿度也很重要。以最大饱和度百分比衡量，一致认为 75％ 至 95％ 的湿度很好。我们将 85％设置为理想值，可接受的浮动为 10％。这些值适用于大多数奶酪。为了获得特定的结果，例如外皮的特定状况，奶酪制造商会在老化过程中的某个时间调整这些值。

在南部地区，地表附近的天然储藏室的环境温度可能约为 70 度。由于水从屋顶渗入，此类储藏室的相对湿度也可能接近 100％。这些高数值并不是奶酪老化的理想条件。在更北端的地区，天然储藏室的环境温度可以为理想的 50 度。由于我们所处的地理位置，我们需要一些 Azure IoT 干预！

#### 发送和接收遥测

遥测输出的频率是一个重要因素。制冷单元中的温度传感器可能只需每分钟或更短的时间报告一次。飞机上的加速度传感器可能必须至少每秒报告一次。

IoT 设备可能包含一个或多个传感器，并具有一定的计算能力。IoT 设备上可能有 LED 灯，甚至有一个小屏幕。但是，该设备并非旨在供操作人员直接使用。IoT 设备旨在从云中接收其指令。

#### 控制奶酪储藏室设备

在此模块中，我们假设 IoT 奶酪储藏室监控设备具有温度和湿度传感器。该设备具有能够冷却或加热以及加湿或除湿的风扇。设备每隔几秒钟就会将当前的温度和湿度值发送到 IoT 中心。对于奶酪储藏室来说，这种快速的频率是不现实的（也许每 15 分钟或更短的时间就足够了），除非在代码开发过程中需要快速活动！

在本实验中，我们假设风扇可以处于以下三种状态之一：开、关和故障。风扇初始化为关闭状态。在下一个单元，风扇会通过直接方法打开。

我们的物联网设备的另一个功能是它可以接受来自 IoT 中心的期望值。然后，设备可以调节风扇以达到这些期望值。这些值使用称为设备孪生的功能在此模块中编码。所需值将覆盖设备的任何默认设置。

#### 编码样本

该模块中的编码分为三个部分：发送和接收遥测，发送和接收直接方法以及管理设备孪生。

让我们从编写两个应用开始：一个用于设备发送遥测的应用，另一个用于在云中运行以接收遥测的后端服务。你将能够选择首选语言（Node.js 或 C#）和开发环境（Visual Studio Code 或 Visual Studio）。

#### 练习 1：使用 IoT 中心门户创建自定义 Azure IoT 中心

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| IoT 设备 | CheeseCaveID |

#### 练习 2：写入发送和接收遥测的代码

在本单元结束时，你将会发送和接收遥测。

#### 练习 2：创建第二个应用以接收遥测

现在我们有了一个抽出遥测的设备，我们需要使用一个后端应用（也连接到我们的 IoT 中心）来监听遥测。

#### 练习 3：编写代码以调用直接方法

在本单元中，我们将代码添加到设备应用中，以实现打开风扇的直接方法。接下来，我们将代码添加到后端服务应用以调用此直接方法。

后端应用中调用直接方法的调用可以包含多个参数作为有效负载的一部分。直接方法通常用于打开和关闭设备的功能，或指定设备的设置。

#### 练习 4：为设备孪生写入代码

在本练习中，我们将向设备应用和后端服务应用添加一些代码，以显示运行中的设备孪生同步。

提醒一下，一对设备孪生包含四种类型的信息：

* **标签**：设备上不可见的设备信息。
* **所需属性**：后端应用指定的所需设置。
* **报告的属性**：设备上报告的设置值。
* **设备标识属性**：标识设备的只读信息。

设备孪生旨在与真正的 IoT 中心设备进行查询并自动同步。可以随时通过后端应用查询设备孪生。该查询可以返回设备的当前状态信息。获取此数据不涉及对设备的调用，因为设备和设备孪生将自动同步。设备孪生的许多功能由 Azure IoT 提供，因此无需编写太多代码即可使用它们。

孪生设备的功能和直接方法之间存在一些重叠。我们可以使用直接方法设置所需的属性，这似乎是一种直观的处理方式。但是，如果需要访问直接设置，则使用直接方法将要求后端应用明确记录这些设置。使用设备孪生，默认情况下会存储和维护此信息。

## LAB_AK_16

### 实验室场景

假设你经营一家提供解决方案的公司，以将奶酪储藏室的温度和湿度维护和监控在最佳水平。长期以来，你一直与美食奶酪制作公司合作，并与这些认可你的产品质量的客户建立了长期信任关系。

你的解决方案包括安装在储藏室中的传感器和气候系统，可实时报告温度和湿度，并且还包括一个在线门户，客户可将该门户用来监视和远程操作其设备，这样可使温度和湿度适合他们在储藏室中储藏的奶酪类型，或便于微调环境来使其奶酪实现完美老化。

你的公司一直在改进设备上运行的软件，以更好地适应客户的不同奶酪以及他们用来储藏奶酪的各种类型的储藏室。除了功能更新之外，你还希望确保部署在客户位置的设备具有最新的安全补丁程序，以确保隐私并防止黑客控制系统。为此，你需要通过远程更新其固件来使设备保持最新状态。

#### 练习 1：创建 Azure IoT 中心和设备 ID

本实验假定可以使用以下资源：

| 资源类型 | 资源名称 |
| :-- | :-- |
| 资源组 | AZ-220-RG |
| IoT 中心 | AZ-220-HUB-_{YOUR-ID}_ |
| IoT 设备 | SimulatedSolutionThermostat |

#### 练习 2：写入代码以模拟实现固件更新的设备

在此任务结束时，你将拥有一个等待来自 IoT 中心的固件更新请求的设备模拟器。

开始在 IoT 设备上进行首次固件更新之前，请花一点时间查看实施此操作的实际含义以及 Azure IoT 中心如何帮助完成该过程。
##### 更新 IoT 设备的固件意味着什么？

IoT 设备通常由优化的操作系统供电，有时甚至直接在芯片上运行代码（无需实际的操作系统）。为了更新在此类设备上运行的软件，最常用的方法是刷写整个软件包的新版本，包括 OS 以及在其上运行的应用（称为固件）。

由于每个设备都有特定用途，因此其固件也非常具体，并针对设备用途以及可用受限资源进行了优化。

固件的更新过程也可能非常特定于硬件本身以及硬件制造商的工作方式。这意味着部分固件更新过程不通用，你需要联系设备制造商以获取固件更新过程的详细信息（除非你正自行开发硬件，这意味着你很可能知道固件更新过程的详细信息） 。

虽然固件更新可以在设备上手动应用，但考虑到 IoT 解决方案规模的快速增长，这已不再可能。现在，固件更新通常是以无线 (OTA) 方式进行的，通过云远程管理新固件部署。

IoT 设备的所有无线固件更新都有一组共同点：

1. 固件版本是唯一标识的
1. 固件采用二进制文件格式，设备需要从在线来源获取固件
1. 固件是存储在本地的某种物理存储形式（ROM 存储器、硬盘驱动器...）
1. 设备制造商提供了更新固件所需设备操作的描述。

##### Azure IoT 中心自动设备管理

Azure IoT 中心提供高级支持，用于在单个设备上和设备集合上实施设备管理操作。[自动设备管理](https://docs.microsoft.com/azure/iot-hub/iot-hub-auto-device-config)功能允许简单地配置一组操作，触发它们，然后监视它们的执行。

在本练习中，你将创建一个负责管理设备孪生所需属性更改的简单模拟器，还将触发一个模拟固件更新的本地过程。对实际设备而言，除了本地固件更新的实际步骤外，整个过程完全相同。然后，你将使用 Azure 门户为单个设备配置和执行固件更新。IoT 中心将使用设备孪生属性将配置更改请求传输到设备并监视进度

#### 练习 3：在单个设备上测试固件更新

在本练习中，我们将使用 Azure 门户创建新的设备管理配置，并将其应用于我们的单个模拟设备。

## LAB_AK_17

### 实验室场景

我们的资产跟踪解决方案正在变得越来越大，并且逐一（甚至通过 DPS）预配设备无法缩放。我们希望通过 x.509 证书身份验证来使用 DPS 自动安全地注册许多设备。在我们的解决方案中，我们将使用传感器来跟踪我们正在运输的资产。每次将传感器添加到运输箱中时，将通过 DPS 自动预配。我们希望为仓库经理提供一个指标，说明带有“标记”的箱子数量，并需要从 IoT 中心计算设备连接事件。

在本实验室中，你将使用 CA x.509 根证书链在设备预配服务 (DPS) 中设置组注册。你将配置链接的 IoT 中心以使用监视功能来跟踪已连接设备的数量和发送的遥测消息，以及将连接事件发送到日志。另外，你将创建一个警报，该警报将基于连接的平均设备数触发。你将配置 10 个模拟的 IoT 设备，这些设备将使用在 CA 根证书链上生成的设备 CA 证书向 DPS 进行身份验证。IoT 设备将配置为将遥测发送到 IoT 中心。

#### 练习 1：验证实验室先决条件

[待定]

#### 练习 2：通过 IoT 中心设置和使用指标和诊断日志

如果 IoT 中心解决方案正在生产中运行，则需要设置一些指标并启用诊断日志。然后，如果出现问题，则需要查看数据，这将帮助你诊断问题并更快地解决问题。在本实验中，你将看到如何启用诊断日志以及如何检查它们的错误。你还将设置一些要监视的指标，并在指标达到特定边界时发出警报。

例如，当连接的设备数超过特定阈值时，或者当使用的消息数接近 IoT 中心每天允许的消息配额时，你可能会向收到一封电子邮件。

#### 练习 3：启用日志记录

Azure 资源日志是 Azure 资源发出的描述其内部操作的平台日志。所有资源日志共享一个通用的顶级架构，每个服务都可以灵活地为自己的事件发出独特的属性。

#### 练习 4：配置警报

现在让我们创建一个警报。在监视数据中发现重要情况时，警报会主动通知你。它们允许你在系统用户注意到之前识别并解决问题。在我们的资产跟踪方案中，我们使用传感器来跟踪我们正在运输的资产。每次将传感器添加到运输箱中时，将通过 DPS 自动预配。我们希望为仓库经理提供一个指标，说明带有“标记”的箱子数量，并需要从 IoT 中心计算设备连接事件。

在此任务中，我们将添加一个警报，当连接 5 个或更多设备时，该警报将通知仓库经理。

#### 练习 5：模拟传感器

作为资产跟踪方案的一部分，我们需要具有可模拟用于在运输过程中跟踪资产的标签的设备。激活每个设备后，应使用自动设备预配连接到 IoT 解决方案并开始发送遥测。为了能够自动连接，每个设备都需要自己的 X509 证书，该证书是用于创建组注册的根证书链的一部分。

在此任务中，我们将验证现有环境，执行任何必要的设置，生成 10 个设备证书，并配置将模拟 10 台设备的控制台应用程序。

#### 练习 6：模拟设备

在此任务中，我们将从根证书生成 X509 证书。然后，我们将在控制台应用程序中使用这些证书，该应用程序将模拟 10 台连接到 DPS 并将遥测发送到 IoT 中心的设备。

#### 练习 7：查看指标、警报和存档

[待定]

## LAB_AK_18

**MISING**

## LAB_AK_19

### 实验室场景

Contoso 在构建所有解决方案时都考虑到了安全性。但是，他们希望了解如何更好地在其所有本地和云工作负载（包括其 Azure IoT 解决方案）中获得安全性的统一视图。另外，在新设备上载入时，我们希望跨工作负载（叶设备、Microsoft Edge 设备、IoT 中心）应用安全策略，以确保符合安全标准并改进安全状况。

Contoso 正在增加一条配备了新 IoT 设备的全新装配线，以帮助解决增加新订单带来的运输和包装需求。你想要确保所有新设备都受到保护，还希望能够看到安全建议，以继续在完整的端到端 IoT 解决方案中提高解决方案的安全性。你将开始针对解决方案使用 Azure IoT Center for IoT 进行调查。

#### 练习 1：验证实验室先决条件

[待定]

#### 练习 2：使用 Azure 门户创建 IoT 中心

在此任务中，你将使用 Azure 门户创建 IoT 中心资源。

#### 练习 3：启用适用于 IoT 中心的 Azure 安全中心

适用于 IoT 中心的 Azure 安全中心统一了安全管理，并支持跨混合云工作负载和 Azure IoT 解决方案进行端到端威胁检测和分析。

#### 练习 4：创建并注册新设备

[待定]

#### 练习 5：创建一个安全模块孪生

适用于 IoT 的 Azure 安全中心提供与现有 IoT 设备管理平台的完全集成，使你能够管理设备安全状态并利用现有设备控制功能。适用于 IoT 集成的 Azure 安全中心是通过使用 IoT 中心孪生机制实现的。

适用于 IoT 的 Azure 安全中心使用模块孪生机制，并为每个设备维护一个名为 azureiotsecurity 的安全模块孪生。

安全模块孪生包含与每个设备的设备安全相关的所有信息。

要充分利用适用于 IoT 的 Azure 安全中心功能，你需要为新的 IoT Edge 设备创建、配置和使用这些安全模块孪生。

安全模块孪生 **azureiotsecurity** 可以通过两种方式创建：

* [模块批处理脚本](https://github.com/Azure/Azure-IoT-Security/tree/master/security_module_twin) - 使用默认配置自动为新设备或没有模块孪生的设备创建模块孪生。
* 使用每个设备的特定配置分别手动编辑每个模块孪生。

在此任务中，你将手动创建一个安全模块孪生。

#### 练习 6：部署适用于 IoT 的 Azure 安全中心 C# 安全代理

适用于 IoT 的 Azure 安全中心为通过 IoT 中心记录、处理、聚合和发送安全数据的安全代理提供了参考体系结构。你将添加适用于 C# 的安全代理，以在模拟设备 (Linux VM) 上部署。有基于 C 和 C# 的代理。对于具有更多受限或最少设备资源的设备，建议使用 C 代理。

安全代理支持以下功能：

* 从基础操作系统（Linux、Windows）收集原始安全事件。如需了解有关可用安全数据收集器的更多信息，请参阅《适用于 IoT 的 Azure 安全中心的代理配置》。
* 将原始安全事件聚合为通过 IoT 中心发送的消息。
* 使用现有设备标识或专用模块标识进行身份验证。有关详细信息，请参阅“安全代理身份验证方法”。
* 通过使用 **azureiotsecurity** 模块孪生进行远程配置。要了解更多信息，请参阅《配置适用于 IoT 的 Azure 安全中心代理》。

#### 练习 7：配置解决方案管理

适用于 IoT 的 Azure 安全中心为基于 Azure 的 IoT 解决方案提供了全面的端到端安全性。

通过适用于 IoT 的 Azure 安全中心，即可在一个仪表板上监视整个 IoT 解决方案，从而在 Azure 中显示所有 IoT 设备、IoT 平台和后端资源。

在 IoT 中心启用后，适用于 IoT 的 Azure 安全中心会自动识别其他 Azure 服务，这些服务也已连接到 IoT 中心并与 IoT 解决方案相关。

除了自动关系检测外，你还可以选择要标记为 IoT 解决方案一部分的其他 Azure 资源组。通过这些选择，你可以添加整个订阅、资源组或单个资源。

## LAB_AK_20

### 实验室场景

通过 Azure IoT Central，可轻松监视和管理一系列远程设备。

Azure IoT Central 包含了一系列行之有效的基础技术，但是当需要许多技术时，实施起来可能会很复杂。这些技术包括 Azure IoT 中心、Azure 设备预配系统 (DPS)、Azure Maps、Azure 时序见解、Azure IoT Edge 等。如果需要的粒度比 IoT Central 可用的粒度更多，才需要直接使用这些技术。

本实验室的一个目的是帮助你确定 IoT Central 中是否有足够的功能来支持你可能需要的场景。因此，让我们研究一下 IoT Central 在一个有趣且涉及的场景中可以做些什么。

Contoso 经营着一批冷藏卡车。你在一个城市中有许多客户，并且有一个运营基地。你让每辆卡车运走其中的物品并将其交付给任何一位客户。但是，你的任何一辆卡车上的冷却系统都可能出现故障，如果装载的物品开始熔化，你需要选择指示卡车返回基地，然后将装载的物品卸货。或者，你可以将物品交付给另一位客户，当你意识到物品正在熔化时，该客户所在的位置可能更临近此辆卡车。

为了做出这些决策，你需要了解卡车的最新情况。您需要了解每辆卡车在地图上的位置、冷却系统的状态和物品的状态。

IoT Central 提供了处理此场景所需的全部信息。 

#### 练习 1：创建自定义 IoT Central 应用

[待定]

#### 练习 2：创建设备模板

远程设备和 IoT Central 之间通信的数据在_设备模板_中指定。设备模板封装了数据的所有详细信息，因此设备和 IoT Central 都拥有实现通信所需的所有信息。

在本实验室中，你将为冷藏卡车创建设备模板。

#### 练习 3：监视模拟设备

首先，你将创建一个仪表板，其中显示了设备模板的所有功能。接下来，你将创建一个真实的设备，并记录远程设备应用所需的连接设置。

#### 练习 4：创建免费 Azure 地图帐户

如果你还没有 Azure 地图帐户，则需要创建一个。

#### 练习 5：为真实设备创建编程项目

在此任务中，你将创建一个编程项目来模拟冷藏卡车中的传感器设备。这种模拟使你可以在需要真正的卡车之前就测试代码！

IoT Central 将此模拟视为“真实”，因为设备应用与 IoT Central 应用之间的通信代码对于真实卡车而言是相同的。换句话说，如果你经营一家冷藏卡车公司，你将从与本任务中的代码类似的模拟代码开始。在该代码令你满意时，特定于模拟的代码将替换为接收传感器数据的代码。这种有限更新使以下代码的编写过程成为宝贵的经验。

#### 练习 6：测试你的 IoT Central 设备

完成此任务是 IoT Central 开发中令人兴奋的时刻！最后，你将检查你创建的所有移动零件是否协同工作。

#### 练习 7：创建多台设备

在此任务中，我们考虑了将多辆卡车添加到我们的系统所需的步骤。

