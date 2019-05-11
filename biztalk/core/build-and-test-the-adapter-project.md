---
title: 生成和测试适配器项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b5eb486-99ae-4661-b0d0-d2d363d97b73
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 626777dc4f4e1b15d9d925f7536e99b7974f0b1c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530405"
---
# <a name="build-and-test-the-adapter-project"></a>生成和测试适配器项目
若要测试对 AdapterManagement 项目所做的更改的所有操作，重新生成项目。 成功生成后运行添加适配器元数据向导以确保所有内部和外部 XSD 文件添加到 AdapterManagement 项目。 有关使用添加适配器元数据向导的说明，请参阅[如何向 BizTalk 项目添加适配器元数据](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)。  

 若要测试对配置架构所做的更改，请打开每个属性页生成的 XSD 文件，以确保它们请求和接受正确的数据。 为此，配置发送端口、 接收位置、 发送处理程序，并接收处理程序中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台<strong>。</strong>  

> [!NOTE]
>  适配器可能不具有全部配置架构。 例如，不支持接收消息的发送适配器可能具有仅 TransmitLocation.xsd 和 TransmitHandler.xsd 架构。  

### <a name="to-test-the-transmitlocationxsd-file"></a>若要测试 TransmitLocation.xsd 文件  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**节点，展开**BizTalk 组**，展开**发送端口**节点，指向**新建**，和然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框中**名称**框中，键入发送端口的名称。 展开**传输**节点，并选择**主**节点。  

4. 在右窗格中，在**传输类型值**框中，选择**静态**，然后单击**配置**。 所显示的屏幕应包含您在 TransmitLocation.xsd 文件中指定的字段。  

### <a name="to-test-the-receivelocationxsd-file"></a>若要测试 ReceiveLocation.xsd 文件  

1. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**节点，展开**BizTalk 组**，展开**接收端口**集合中，展开新创建的接收端口或右键单击你想要添加接收位置的接收端口**接收位置**集合中，依次指向**新建**，然后单击**单向接收位置**.  

2. 在中**选择接收端口**对话框框中，选择的端口。  

3. 在中**接收位置属性**对话框中，在左窗格中，选择**常规**节点。  

4. 在中**接收位置属性**对话框中**名称**框中，键入接收位置的名称。  

5. 在中**接收位置属性**对话框，在右窗格中，在**传输类型值**框中，选择**静态**，然后单击**配置**. 所显示的屏幕应包含您在 ReceiveLocation.xsd 文件中指定的字段。  

### <a name="to-test-the-receivehandlerxsd-file"></a>若要测试 ReceiveHandler.xsd 文件  

1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**节点，展开**BizTalk 组**展开**平台设置**，展开**适配器**，单击**静态**，然后单击**BizTalkServerApplication**方向**接收**。  

3. 在结果窗格中，右键单击接收处理程序，然后依次**属性**。 上**常规**选项卡上，单击**属性**。 所显示的屏幕应包含您在 ReceiveHandler.xsd 文件中指定的字段。  

### <a name="to-test-the-transmithandlerxsd-file"></a>若要测试 TransmitHandler.xsd 文件  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**静态**，然后单击**BizTalkServerApplication**方向**发送**。  

2. 在结果窗格中，右键单击接收处理程序，然后依次**属性**。 上**常规**选项卡上，单击**属性**。 所显示的屏幕应包含您在 TransmitHandler.xsd 文件中指定的字段。
