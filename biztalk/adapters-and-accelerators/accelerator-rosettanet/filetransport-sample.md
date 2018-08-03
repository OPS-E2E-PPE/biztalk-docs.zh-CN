---
title: FileTransport 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a4be76ba244418612fe9c4a4996569b3c40b506
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006998"
---
# <a name="filetransport-sample"></a>FileTransport 示例
FileTransport 示例演示如何配置 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]若要使用文件端口而不是 SQL 端口。 FileTransport 示例使用文件传输协议 (FTP) 发送和接收消息，而不是使用 HTTP。  
  
> [!NOTE]
>  此文档假设你安装 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 只是为了进行内部测试或进行演示。 文档中没有涉及任何最低安全帐户或设置。 在执行本主题的所有过程时，都必须使用具有本地管理权限的帐户。  
> 
> [!NOTE]
>  此示例不支持消息附件。  
  
## <a name="filetransport-binding-files"></a>FileTransport 绑定文件  
 FileTransport 示例包含两个绑定文件。 你可以使用这些绑定文件中的任何一个来设置用于 BTARN 业务流程的文件端口。 这些绑定文件位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\FileTransport。 在编辑器（如记事本）中打开每个绑定文件，可查看业务流程、发送端口、接收端口和接收位置的设置，如下所示：  
  
- PrivateInitiatorusingFileDrops.xml  
  
  -   业务流程：Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess  
  
  -   发送端口：PrivateInitiator_To_File  
  
  -   接收端口：File_To_PrivateInitiator  
  
  -   接收位置：File_To_PrivateInitiator  
  
- PrivateResponderusingFileDrops.xml  
  
  -   业务流程：Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess  
  
  -   发送端口：PrivateResponder_To_File  
  
  -   接收端口：File_To_PrivateResponder  
  
  -   接收位置：File_To_PrivateResponder  
  
  以下过程介绍如何使用 BTSTask 命令从绑定文件导入绑定。 有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a>使用“文件存放”文件夹来设置 BTARN  
  
1.  打开 BizTalk 浏览器。  
  
2.  停止两个 LOB SQL 发送端口：PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB。  
  
3.  禁用两个 Lob SQL 接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。  
  
4.  取消登记 Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess。  
  
5.  取消登记 Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess。  
  
6.  创建 \FileDrops 文件夹 C:\Program Files\Microsoft BizTalk 的 BTARN 文件夹下\<版本\>Accelerator for RosettaNet，然后创建在 \FileDrops 下的以下文件夹结构：  
  
    -   \PrivateInitiator  
  
         \FromLOB  
  
         \ToLOB  
  
    -   \PrivateResponder  
  
         \FromLOB  
  
         \ToLOB  
  
7.  运行以下命令（假定 BTARN 安装在 C: 驱动器上）：  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  运行以下命令（假定 BTARN 安装在 C: 驱动器上）：  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. 启动发送端口：PrivateInitiator_To_File 和 PrivateResponder_To_File。  
  
10. 启用接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。  
  
## <a name="see-also"></a>请参阅  
 [消息传送示例](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)