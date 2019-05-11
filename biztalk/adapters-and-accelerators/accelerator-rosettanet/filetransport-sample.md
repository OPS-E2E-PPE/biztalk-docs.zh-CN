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
ms.openlocfilehash: a79759a94b2effd751dd566d62dcdde51395e566
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283716"
---
# <a name="filetransport-sample"></a>FileTransport 示例
FileTransport 示例演示如何配置 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]若要使用文件端口而不是 SQL 端口。 FileTransport 示例使用文件传输协议 (FTP) 来发送和接收消息，而不是 HTTP。  
  
> [!NOTE]
>  本文档假定您在安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]针对内部测试或演示目的。 它不规定任何最低安全帐户或设置。 必须使用具有本主题中的所有过程的本地管理权限的帐户。  
> 
> [!NOTE]
>  此示例不支持消息附件。  
  
## <a name="filetransport-binding-files"></a>FileTransport 绑定文件  
 FileTransport 示例包含两个绑定文件。 可以使用每个绑定文件来设置用于 BTARN 业务流程文件端口。 这些绑定文件位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\FileTransport。 若要查看该业务流程的设置、 发送端口、 接收端口和接收位置，如记事本编辑器中打开每个绑定文件，如下所示。  
  
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
  
  以下过程介绍如何从绑定文件使用 BTSTask 命令导入绑定。 有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a>若要使用文件的放置文件夹设置 BTARN  
  
1.  打开 BizTalk 浏览器。  
  
2.  停止两个 LOB SQL 发送端口： PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB。  
  
3.  禁用两个 Lob SQL 接收端口，LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。  
  
4.  取消登记 Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess。  
  
5.  取消登记 Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess。  
  
6.  创建 \FileDrops 文件夹 C:\Program Files\Microsoft BizTalk 的 BTARN 文件夹下\<版本\>Accelerator for RosettaNet，然后创建在 \FileDrops 下的以下文件夹结构：  
  
    -   \PrivateInitiator  
  
         \FromLOB  
  
         \ToLOB  
  
    -   \PrivateResponder  
  
         \FromLOB  
  
         \ToLOB  
  
7.  运行以下命令 （假定 BTARN 安装在 c： 驱动器上）：  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  运行以下命令 （假定 BTARN 安装在 c： 驱动器上）：  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. 启动发送端口：PrivateInitiator_To_File 和 PrivateResponder_To_File。  
  
10. 启用接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。  
  
## <a name="see-also"></a>请参阅  
 [消息传送示例](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)