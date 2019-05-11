---
title: 将证书添加到服务器上的证书存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 973dc2caa5fd3950a8e1bebb74cf2c3e13806d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378883"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a>将证书添加到服务器上的证书存储
使用以下步骤将证书添加到服务器计算机上的证书 （本地计算机） 存储中的其他人文件夹。  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>若要将证书添加到证书存储区  
  
1.  单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BizTalk Accelerator for SWIFT 管理控制台**。  
  
    > [!NOTE]
    >  如果您仍然可以从前面的过程 （添加的证书，为客户端上的证书存储） 中打开 MMC 窗口，您可以使用它对于此过程。  
  
2.  在管理控制台窗口中，展开**证书 （本地计算机）** 文件夹，然后展开**其他人**。  
  
3.  右键单击**证书**，依次指向**的所有任务**，然后单击**导入**。  
  
4.  在欢迎使用证书导入向导页上，单击**下一步**。  
  
5.  在导入页的文件，单击**浏览**。  
  
6.  在打开的对话框中，转到证书，请选择保存的文件位置**的所有文件**有关**Files of Type**，选择你想要导入，然后单击该证书**打开**。  
  
7.  在导入页的文件，单击**下一步**。  
  
8.  在证书存储页中，确认**将所有证书都放入下列存储**是选择，确保**其他人**中显示**证书存储区**框中，然后依次**下一步**。  
  
9. 在正在完成证书导入向导页上，单击**完成**。  
  
10. 在证书导入向导对话框中，该值指示成功导入，单击**确定**。  
  
11. 对于将在消息修复和新提交中使用其他证书重复步骤 3 至 10。