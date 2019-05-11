---
title: 步骤 4：创建用于接受批处理消息接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a37eb334-c4ae-40d1-a433-bf0ab39c0765
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fca10f31c3de2d82b769cb63a732c7c144a465a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288205"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>步骤 4：创建用于接受批处理消息接收端口
此步骤中，创建并配置要接收传入的批的端口。  

 创建请求-响应 （双向） 接收端口，因为该方案包括一代应用程序的接受为批处理中的单个消息的确认。 在双向模式下，MLLP 接收适配器将不接受新的传入消息，直到接收管道都生成确认 (ACK) 前面的消息。  

## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>创建用于接受批处理消息的接收端口  

1. 打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**。  

   > [!NOTE]
   >  在 BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。  

2. 右键单击**接收端口**，选择**新建**，然后选择**请求响应接收端口**。  

3. 有关**名称**，输入**Tutorial_2WayReceive**。  

4. 选择**Apply**以绑定端口，然后选择**接收位置**。  

5. 选择**新**。  

6. 有关**名称**，输入**Tutorial_2WayReceive**。

7. 在中**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。  

8. 选择 **“配置”**。 在中**MLLP 传输属性**中，配置以下内容，并选择**确定**。  


   |           使用此选项           |                                                                                                                                                                                                     执行的操作                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **连接重试时间 （秒）** |                                                                 新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>要尝试重新连接已删除或已关闭连接之前等待的时间上限。 才可用**连接由发起**设置为**本地**。<br/><br/>默认值为 20 秒的时间。                                                                  |
   | **由启动的连接**  | 新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入**本地**MLLP 接收位置可以启动与远程 LOB 服务器的连接。 这是新的选项。<br/><br/>输入**远程**MLLP 接收位置继续侦听从远程 LOB 服务器的连接。 这是向后兼容的默认选项。<br/><br/>默认值为远程。 |
   |     **连接名称**      |                                                                                                                                                                                                  输入**2Way**。                                                                                                                                                                                                   |
   |        **主机名**         |                                                                                                                                              特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>输入**localhost**。                                                                                                                                               |
   |     **本地主机名**      |                                                                            新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 您还可以输入**localhost**。                                                                             |
   |           **端口**           |                                                                                                                                                特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>设置为**21000**。                                                                                                                                                |
   |        **本地端口**        |                                                                                       新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入本地主机连接的 TCP 端口号。 仅在**连接由发起**是**远程**。 <br/><br/>设置为**21000**。                                                                                        |
   |       **远程主机**        |                                                                                                   新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或远程 LOB 服务器的 IP 地址。 才可用**连接由发起**设置为**本地**。                                                                                                    |
   |       **远程端口**        |                                                                                      新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入远程主机连接的 TCP 端口号。 才可用**连接由发起**设置为**本地**。<br/><br/>设置为**21000**。                                                                                       |


9. 在接收位置属性中，选择以下项：  


   |       使用此选项       |                         执行的操作                          |
   |----------------------|-------------------------------------------------------------|
   | **接收处理程序**  | 选择**BizTalkServerApplication**从下拉列表 |
   | **接收管道** |    选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**     |
   |  **发送管道**   |      选择**BTAHL72XPipelines.BTAHL72XSendPipeline**      |


10. 选择**确定**以保存所做的更改。  

11. 启用通过右键单击它，刚刚创建的接收位置，然后选择**启用**。  

## <a name="next-step"></a>下一步
[步骤 5：创建用于传递消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)