---
title: "如何更新的程序集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163b06706652b1f65b9a76e3feea8911a2ca4c88
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-an-assembly"></a>如何更新的程序集
本主题介绍如何更新的程序集和程序集部署到使用 Visual Studio 2010 的应用程序的版本。  
  
> [!NOTE]  
>  如果你使用新版本进行更新程序集，你不需要重新启动应用程序。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。  
  
## <a name="updating-an-assembly"></a>更新程序集  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a>若要增加程序集的版本号  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
2.  在**项目设计器**，单击**应用程序**选项卡。  
  
3.  在右窗格中，单击**程序集信息**。  
  
4.  在**程序集信息**对话框框中，为指定值**程序集版本**字段以增加程序集版本号。 应该只递增主版本号或次版本号。 主版本号是序列中的第一个数字 (***n***.0.0.0); 的次版本号是序列中的第二个数字 (0。***n*** .0.0)。 BizTalk Server 将无法识别序列，如 0.0 中更高版本的版本编号更改。 ***n*** .0 或 0.0.0。***n***.  
  
5.  单击**确定**关闭**程序集信息**对话框。  
  
6.  保存项目。  
  
    > [!NOTE]  
    >  使用管道设计器和 BizTalk 浏览器对象模型，可以避免在递增程序集版本时出现架构冲突。  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a>若要更改的应用程序程序集部署到  
  
1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
2.  在**项目设计器**，单击**部署**选项卡。  
  
3.  在右窗格中，指定中的应用程序名称**应用程序名称**字段。  
  
4.  确保**安装到全局程序集缓存**属性设置为**True**。  
  
    > [!NOTE]  
    >  在您部署该解决方案时，这些程序集将部署到新应用程序中并安装在 GAC 中。