---
title: 如何注册和删除 BizTalk 程序集查看器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b78aeb8f0ebdbc1a7e05c8cfc45137b991b6eb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384395"
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a>如何注册和删除 BizTalk 程序集查看器
在 BizTalk Server 安装期间不自动注册 BizTalk 程序集查看器。 若要注册或删除 BizTalk 程序集查看器，请执行以下步骤。  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a>若要将程序集查看器添加到 Windows 注册表  
  
1.  从**启动**菜单上，单击**运行**。  
  
2.  在运行对话框中，键入**cmd**。  
  
3.  从命令行中，导航到\< *BizTalk Server 安装文件夹*\>\developer tools\ BTSAsmExt.dll 所在的位置。  
  
4.  在命令行中，键入：  
  
     regsvr32 BTSAsmExt.dll  
  
5.  若要开始使用程序集视图，请先注销，然后再登录计算机。  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a>若要从 Windows 注册表删除程序集查看器  
  
1.  从**启动**菜单上，单击**运行**。  
  
2.  在中**运行**对话框中，键入**cmd**。  
  
3.  从命令行中，导航到\< *BizTalk Server 安装文件夹*\>\developer tools\ BTSAsmExt.dll 所在的位置。  
  
4.  在命令行中，键入：  
  
     regsvr32/u BTSAsmExt.dll  
  
5.  若要完成删除，先注销，然后再登录计算机。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 程序集查看器查看程序集](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)