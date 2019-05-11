---
title: 将证书添加到客户端上的证书存储 |Microsoft Docs
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
ms.assetid: 9e2722ee-dd6f-4b14-9796-2f2157e8cad2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a953ceaddd02df5e258ceb3034a29f6e56aff7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378895"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-client"></a>将证书添加到客户端上的证书存储
使用以下步骤将证书添加到每个客户端计算机上的证书存储中的个人文件夹。 必须将证书添加到证书-当前用户存储区中的个人文件夹。  
  
> [!IMPORTANT]
>  如果您的证书不通过分发企业信任证书颁发机构，你必须导入到客户端计算机上的证书颁发机构的根证书。 否则，您的个人证书将无法工作。 证书颁发机构的证书导入到证书 （本地计算机） 节点中的受信任的根证书颁发机构文件夹中。  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>若要将证书添加到证书存储区  
  
1.  单击 **“启动”**，再单击 **“运行”**。 输入**mmc**，然后单击**确定**。  
  
2.  在 console1 对话框中，单击**文件**，然后单击**添加/删除管理单元中**。  
  
3.  在添加/删除管理单元对话框中，单击**添加**。  
  
4.  在添加独立管理单元对话框中，单击**证书**，然后单击**添加**。  
  
5.  在证书管理单元对话框中，单击**我的用户帐户**，然后单击**完成**。  
  
6.  在添加独立管理单元对话框中，单击**证书**，然后单击**添加**。  
  
7.  在证书管理单元对话框中，单击**计算机帐户**，然后单击**下一步**。  
  
8.  在选择计算机对话框中，请确保**本地计算机**已选中，然后单击**完成**。  
  
9. 在添加独立管理单元对话框中，单击**关闭**。  
  
10. 在添加/删除管理单元对话框中，单击**确定**。  
  
11. 在中**控制台根节点**窗格中的控制台 1 对话框中，展开**证书-当前用户**文件夹。  
  
12. 下**证书-当前用户**，展开**个人**。  
  
13. 右键单击**证书**，依次指向**的所有任务**，然后单击**导入**。  
  
14. 在欢迎使用证书导入向导页上，单击**下一步**。  
  
15. 在导入页的文件，单击**浏览**。  
  
16. 在打开的对话框中，转到证书，请选择保存的文件位置**的所有文件**有关**Files of Type**，选择你想要导入，然后单击该证书**打开**。  
  
17. 在导入页的文件，单击**下一步**。  
  
18. 在证书存储页中，确认**将所有证书都放入下列存储**是选择，确保**个人**显示在**证书存储区**框中，然后依次**下一步**。  
  
19. 在正在完成证书导入向导页上，单击**完成**。  
  
20. 在证书导入向导对话框中，该值指示成功导入，单击**确定**。  
  
21. 对于将在消息修复和新提交中使用其他证书重复步骤 13 到 20。