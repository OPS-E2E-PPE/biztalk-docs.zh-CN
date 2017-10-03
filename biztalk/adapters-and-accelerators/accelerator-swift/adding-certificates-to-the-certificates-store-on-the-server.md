---
title: "将证书添加到服务器上的证书存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a>将证书添加到服务器上的证书存储
使用以下步骤将证书添加到服务器计算机上的证书 （本地计算机） 存储中的其他人文件夹。  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>若要将证书添加到证书存储  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BizTalk Accelerator for SWIFT 管理控制台**。  
  
    > [!NOTE]
    >  如果您还有 MMC 窗口中打开从前面的过程 （向客户端上的证书存储的添加证书），你可以将其用于此过程。  
  
2.  在管理控制台窗口中，展开**证书 （本地计算机）**文件夹，然后展开**其他人**。  
  
3.  右键单击**证书**，指向**所有任务**，然后单击**导入**。  
  
4.  在欢迎使用证书导入向导页上，单击**下一步**。  
  
5.  在导入页文件，单击**浏览**。  
  
6.  在打开的对话框中，移动到您的证书，选择保存的文件位置**所有文件**为**文件类型**，选择你想要导入，然后单击证书**打开**。  
  
7.  在导入页文件，单击**下一步**。  
  
8.  在证书存储页中，确认**将所有证书都放入下列存储**是选择，验证**其他人**中显示**证书存储区**框中，并依次**下一步**。  
  
9. 在正在完成证书导入向导页上，单击**完成**。  
  
10. 在证书导入向导对话框中，该值指示成功的导入，单击**确定**。  
  
11. 对于其他证书将在消息修复和新的提交中使用重复步骤 3-10。