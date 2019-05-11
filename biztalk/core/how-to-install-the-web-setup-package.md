---
title: 如何安装 Web 安装包 |Microsoft Docs
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
ms.openlocfilehash: bb29badb7f3966a094b6131d7ecbf4fd41401116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384877"
---
# <a name="how-to-install-the-web-setup-package"></a><span data-ttu-id="1d16d-102">如何安装 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="1d16d-102">How to Install the Web Setup Package</span></span>
<span data-ttu-id="1d16d-103">使用分发文件夹的内容设置的目标计算机上的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="1d16d-103">Use the contents of the distribution folder to setup the Web service on a destination computer.</span></span>  
  
### <a name="to-install-the-web-setup-package"></a><span data-ttu-id="1d16d-104">若要安装 Web 安装包</span><span class="sxs-lookup"><span data-stu-id="1d16d-104">To install the Web setup package</span></span>  
  
1.  <span data-ttu-id="1d16d-105">将复制到目标计算机上的分发文件夹。</span><span class="sxs-lookup"><span data-stu-id="1d16d-105">Copy the distribution folder onto the destination computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1d16d-106">目标计算机必须安装的 BizTalk Server 运行时和必需的 BizTalk 程序集部署并安装在全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="1d16d-106">The destination computer must have the BizTalk Server runtime installed and the necessary BizTalk assemblies deployed and installed in the global assembly cache.</span></span>  
  
2.  <span data-ttu-id="1d16d-107">运行。MSI 文件安装 Web 服务，然后按照安装向导会提示。</span><span class="sxs-lookup"><span data-stu-id="1d16d-107">Run the .MSI file to install the Web service and follow the setup wizard prompts.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1d16d-108">当向导提示您为虚拟目录中删除"_Setup"后缀。删除后缀可确保接收位置地址与 Web 服务.asmx 文件匹配。</span><span class="sxs-lookup"><span data-stu-id="1d16d-108">Remove the "_Setup" suffix when the wizard prompts you for the virtual directory.Removing the suffix ensures that the receive location addresses match the Web service .asmx files.</span></span>  
  
3.  <span data-ttu-id="1d16d-109">验证虚拟目录的安全设置正确进行授权。</span><span class="sxs-lookup"><span data-stu-id="1d16d-109">Verify that the security settings for the virtual directory are correct for authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d16d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d16d-110">See Also</span></span>  
 [<span data-ttu-id="1d16d-111">在无 Visual Studio 的计算机上部署已发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="1d16d-111">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)