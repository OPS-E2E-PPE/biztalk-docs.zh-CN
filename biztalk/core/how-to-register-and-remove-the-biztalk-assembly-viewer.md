---
title: "如何注册和删除 BizTalk 程序集查看器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deae453be1a89049f223e2da9813e449d68eeb07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a>如何注册和删除 BizTalk 程序集查看器
BizTalk 程序集查看器在 BizTalk Server 安装期间不自动注册。 若要注册或删除 BizTalk 程序集查看器，请执行以下步骤。  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a>向 Windows 注册表添加程序集查看器  
  
1.  从**启动**菜单上，单击**运行**。  
  
2.  在运行对话框中，键入**cmd**。  
  
3.  从命令行中，导航到\< *BizTalk Server 安装文件夹*> \Developer Tools\ BTSAsmExt.dll 所在的位置。  
  
4.  在命令行提示符处键入以下命令：  
  
     regsvr32 BTSAsmExt.dll  
  
5.  若要开始使用程序集视图，先注销，然后再登录该计算机。  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a>从 Windows 注册表删除程序集查看器  
  
1.  从**启动**菜单上，单击**运行**。  
  
2.  在**运行**对话框中，键入**cmd**。  
  
3.  从命令行中，导航到\< *BizTalk Server 安装文件夹*> \Developer Tools\ BTSAsmExt.dll 所在的位置。  
  
4.  在命令行提示符处键入以下命令：  
  
     regsvr32/u BTSAsmExt.dll  
  
5.  若要完成删除，先注销，然后再登录该计算机。  
  
## <a name="see-also"></a>另请参阅  
 [查看具有 BizTalk 程序集查看器的程序集](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)