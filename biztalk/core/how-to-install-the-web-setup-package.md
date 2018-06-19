---
title: 如何安装的 Web 安装程序包 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
ms.assetid: c6b38a2f-ad07-4ccd-b267-9e3510df88c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21fbacd76598a3a86cfa70b4761bc74420afe561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254125"
---
# <a name="how-to-install-the-web-setup-package"></a><span data-ttu-id="403bc-102">如何安装 Web 安装程序包</span><span class="sxs-lookup"><span data-stu-id="403bc-102">How to Install the Web Setup Package</span></span>
<span data-ttu-id="403bc-103">使用分发文件夹的内容在目标计算机上安装 Web Services。</span><span class="sxs-lookup"><span data-stu-id="403bc-103">Use the contents of the distribution folder to setup the Web service on a destination computer.</span></span>  
  
### <a name="to-install-the-web-setup-package"></a><span data-ttu-id="403bc-104">安装 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="403bc-104">To install the Web setup package</span></span>  
  
1.  <span data-ttu-id="403bc-105">将复制到目标计算机上的分发文件夹。</span><span class="sxs-lookup"><span data-stu-id="403bc-105">Copy the distribution folder onto the destination computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="403bc-106">目标计算机必须安装 BizTalk Server 运行时，并在全局程序集缓存中部署和安装了所需的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="403bc-106">The destination computer must have the BizTalk Server runtime installed and the necessary BizTalk assemblies deployed and installed in the global assembly cache.</span></span>  
  
2.  <span data-ttu-id="403bc-107">运行。MSI 文件以安装 Web 服务然后按照安装向导会提示。</span><span class="sxs-lookup"><span data-stu-id="403bc-107">Run the .MSI file to install the Web service and follow the setup wizard prompts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="403bc-108">当向导提示您输入虚拟目录时，请删除“_Setup”后缀，从而确保接收位置地址与 Web Services .asmx 文件匹配。</span><span class="sxs-lookup"><span data-stu-id="403bc-108">Remove the "_Setup" suffix when the wizard prompts you for the virtual directory.Removing the suffix ensures that the receive location addresses match the Web service .asmx files.</span></span>  
  
3.  <span data-ttu-id="403bc-109">验证虚拟目录的安全设置是否正确，以便进行授权。</span><span class="sxs-lookup"><span data-stu-id="403bc-109">Verify that the security settings for the virtual directory are correct for authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403bc-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="403bc-110">See Also</span></span>  
 [<span data-ttu-id="403bc-111">部署非 Visual Studio 计算机上的发布的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="403bc-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)