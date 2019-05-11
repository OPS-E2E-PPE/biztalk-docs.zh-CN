---
title: 步骤 5：创建接收端口用于接收 HIS 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: c0b311d8-541c-4c21-a514-c93092c36fe2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec438b05e7e1e684f66d8f25d3d5692260a9fa5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287992"
---
# <a name="step-5-create-the-receive-port-for-accepting-his-messages"></a>步骤 5：创建用于接收 HIS 消息接收端口
在此步骤中创建接收端口，以指定发送的医院信息系统 (HIS) 的传入消息的位置。 使用以下过程来创建用于接收查询响应消息从 ADT 系统使用最少的较低层协议 (MLLP) 适配器的接收端口。  

## <a name="create-the-hisreceiveport-receive-port"></a>创建 HIS_ReceivePort 接收端口  

1. 打开**BizTalk Server 管理**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk Application 1**。  

2. 右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。   

3. 有关**名称**，输入**HIS_ReceivePort**。  

4. 选择**Apply**以绑定端口，然后选择**接收位置**。  

5. 选择**新**。  

6. 有关**名称**，输入**HIS_Receive**。  

7. 在中**传输**部分中，选择**类型**，然后选择**MLLP**从下拉列表。  

8. 选择 **“配置”**。 在中**MLLP 传输属性**中，配置以下内容，并选择**确定**。  


   |           使用此选项           |                                                                                                                                                                                                     执行的操作                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **连接重试时间 （秒）** |                                                                 新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>要尝试重新连接已删除或已关闭连接之前等待的时间上限。 才可用**连接由发起**设置为**本地**。<br/><br/>默认值为 20 秒的时间。                                                                  |
   | **由启动的连接**  | 新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入**本地**MLLP 接收位置可以启动与远程 LOB 服务器的连接。 这是新的选项。<br/><br/>输入**远程**MLLP 接收位置继续侦听从远程 LOB 服务器的连接。 这是向后兼容的默认选项。<br/><br/>默认值为远程。 |
   |     **连接名称**      |                                                                                                                                                                                             输入**HIS_ReceiveMLLP**。                                                                                                                                                                                             |
   |        **主机名**         |                                                                                                                                              特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>输入**localhost**。                                                                                                                                               |
   |     **本地主机名**      |                                                                            新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或 IP 地址的本地[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。 您还可以输入**localhost**。                                                                             |
   |           **端口**           |                                                                                                                                                特定于[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]和较旧版本。 <br/><br/>设置为**23000**。                                                                                                                                                |
   |        **本地端口**        |                                                                                       新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入本地主机连接的 TCP 端口号。 仅在**连接由发起**是**远程**。 <br/><br/>设置为**23000**。                                                                                        |
   |       **远程主机**        |                                                                                                   新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入的 DNS 名称或远程 LOB 服务器的 IP 地址。 才可用**连接由发起**设置为**本地**。                                                                                                    |
   |       **远程端口**        |                                                                                      新开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。 <br/><br/>输入远程主机连接的 TCP 端口号。 才可用**连接由发起**设置为**本地**。<br/><br/>设置为**23000**。                                                                                       |


9. 设置**接收处理程序**到**BizTalkServerApplication**。  

10. 设置**接收管道**到**BTAHL72XPipelines.BTAHL72XReceivePipeline**。  

11. 选择**确定**以保存所做的更改。  

12. 启用通过右键单击它，刚刚创建的接收位置，然后选择**启用**。  

## <a name="next-step"></a>下一步  
[步骤 6：创建用于传递查询消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)