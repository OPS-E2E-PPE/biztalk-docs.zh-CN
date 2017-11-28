---
title: "如何将 Web 安装程序包分发 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7e6277045593360cbdfe57848f7313054b60f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-distribute-the-web-setup-package"></a><span data-ttu-id="4ffb5-102">如何将 Web 安装程序包分发</span><span class="sxs-lookup"><span data-stu-id="4ffb5-102">How to Distribute the Web Setup Package</span></span>
<span data-ttu-id="4ffb5-103">创建安装包后，还需要创建一个分发文件夹以将 MSI 文件和 BindingInfo.xml 文件复制到其中来安装 Web Services。</span><span class="sxs-lookup"><span data-stu-id="4ffb5-103">After you create the installation package, you need to create a distribution folder where a MSI file and a BindingInfo.xml file are copied to set up the Web service.</span></span>  
  
### <a name="to-distribute-the-web-setup-package"></a><span data-ttu-id="4ffb5-104">分发 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="4ffb5-104">To distribute the Web setup package</span></span>  
  
1.  <span data-ttu-id="4ffb5-105">创建一个分发文件夹以包含安装文件。</span><span class="sxs-lookup"><span data-stu-id="4ffb5-105">Create a distribution folder to contain your setup files.</span></span>  
  
2.  <span data-ttu-id="4ffb5-106">将 .MSI 文件从 Web 安装项目输出文件夹复制到该分发文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ffb5-106">Copy the .MSI file from the Web Setup project output folder to the distribution folder.</span></span>  
  
3.  <span data-ttu-id="4ffb5-107">将 BindingInfo.xml 文件从 ASP.NET Web Services 项目文件夹中的临时文件夹复制到该分发文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ffb5-107">Copy the BindingInfo.xml file from the temp folder in the ASP.NET Web Service project folder to the distribution folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ffb5-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ffb5-108">See Also</span></span>  
 [<span data-ttu-id="4ffb5-109">部署非 Visual Studio 计算机上的发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="4ffb5-109">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)