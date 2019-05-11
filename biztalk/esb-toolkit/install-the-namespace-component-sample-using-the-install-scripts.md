---
title: 将使用安装脚本 Namespace 组件示例安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66046ef4-91a2-4fe7-93ad-3b8137294411
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e8a802a9c811695bdaee66fbd623ef4b11ba41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399898"
---
# <a name="install-the-namespace-component-sample-using-the-install-scripts"></a><span data-ttu-id="6e7ee-102">安装使用安装脚本的 Namespace 组件示例</span><span class="sxs-lookup"><span data-stu-id="6e7ee-102">Install the Namespace Component Sample Using the Install Scripts</span></span>
<span data-ttu-id="6e7ee-103">本部分介绍如何从使用提供的 Windows 安装程序文件安装 Namespace 组件示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-103">This section describes how you can install the Namespace Component sample from the Windows Installer file provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="6e7ee-104">**若要从安装脚本安装 Namespace 组件示例**</span><span class="sxs-lookup"><span data-stu-id="6e7ee-104">**To install the Namespace Component sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="6e7ee-105">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="6e7ee-106">在中**运行**对话框中，键入**cmd**，然后按 ENTER 以打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6e7ee-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="6e7ee-107">运行以下命令，替换*\<路径\>* 参数替换为你想要安装的.cmd 文件的完整路径 （在此版本中的默认路径是 \Source\Samples\Namepace\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="6e7ee-107">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\Namepace\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```