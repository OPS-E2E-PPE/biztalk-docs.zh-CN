---
title: 如何配置虚拟目录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4a0e35a4d88c9f8a64074cef40a9c701e5e7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385979"
---
# <a name="how-to-configure-the-virtual-directory"></a>如何配置虚拟目录
本主题介绍配置虚拟目录和验证用户的应用程序的过程。  
  
### <a name="to-configure-the-virtual-directory"></a>若要配置的虚拟目录  
  
1.  %Systemdrive%上创建一个文件夹以将配置为虚拟目录。  
  
2.  单击**启动**，依次指向**程序**，单击**管理工具**，然后单击**Internet Information Services (IIS) Manager**。  
  
3.  展开**\<服务器名称\>** ，然后展开**站点**。  
  
4.  右键单击**Default Web Site**然后单击**添加虚拟目录**。  
  
5.  在中**添加虚拟目录**对话框框中，键入别名。  
  
6.  键入在步骤 1 中创建的文件夹的路径。 此外，也可以单击 **（...）** 以浏览到文件夹位置。  
  
7.  单击“确定” 。 该文件夹将显示下**Default Web Site**文件夹。  
  
8.  右键单击该文件夹，然后单击**转换为应用程序**。  
  
9. 在中**添加应用程序**对话框中，单击**确定**。 该文件夹转换为应用程序 （您可以看到图标 – 从文件夹图标变为网站图标中的更改）。  
  
## <a name="see-also"></a>请参阅  
 [保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)