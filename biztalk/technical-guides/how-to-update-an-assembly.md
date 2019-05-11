---
title: 如何更新程序集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68af9966181209b50a4cfb5ee484264d32c60d4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401807"
---
# <a name="how-to-update-an-assembly"></a>如何更新程序集
本主题介绍如何更新的程序集和应用程序程序集部署到使用 Visual Studio 2010 版本。  
  
> [!NOTE]  
>  如果要使用新版本更新程序集，您不需要重新启动该应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。  
  
## <a name="updating-an-assembly"></a>更新的程序集  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a>若要递增程序集的版本号  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
2.  在中**项目设计器**，单击**应用程序**选项卡。  
  
3.  在右窗格中，单击**程序集信息**。  
  
4.  在中**程序集信息**对话框框中，为指定值**程序集版本**字段以增加程序集的版本号。 应增加仅主要或次要版本数。 主版本号是序列中的第一个数字 (***n***.0.0.0); 次版本号是序列中的第二个数字 (0。***n***.0.0)。 BizTalk Server 将无法识别版本号的更改是在序列中，例如 0.0 更高版本。***n***.0 或 0.0.0。***n***。  
  
5.  单击**确定**以关闭**程序集信息**对话框。  
  
6.  保存项目。  
  
    > [!NOTE]  
    >  使用管道设计器和 BizTalk 浏览器对象模型以避免架构冲突时递增程序集版本。  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a>若要更改程序集部署到的应用程序  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
2.  在中**项目设计器**，单击**部署**选项卡。  
  
3.  在右窗格中，指定在应用程序名称**应用程序名称**字段。  
  
4.  絋粄**安装到全局程序集缓存**属性设置为**True**。  
  
    > [!NOTE]  
    >  在部署解决方案时，将部署到新的应用程序并安装到 GAC 中程序集。