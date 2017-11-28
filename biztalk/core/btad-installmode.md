---
title: "BTAD_InstallMode |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BTAD_InstallMode [environment variable]
ms.assetid: b0ca48b8-c672-4704-9a04-2c6f159e57be
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2bcb527bda0a8ee2bfb36b06d317d952b48e699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btadinstallmode"></a><span data-ttu-id="9ca99-102">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="9ca99-102">BTAD_InstallMode</span></span>
<span data-ttu-id="9ca99-103">BTAD_InstallMode 描述 BizTalk 应用程序部署的安装模式。</span><span class="sxs-lookup"><span data-stu-id="9ca99-103">BTAD_InstallMode describes the installation mode for BizTalk application deployment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ca99-104">注释</span><span class="sxs-lookup"><span data-stu-id="9ca99-104">Remarks</span></span>  
 <span data-ttu-id="9ca99-105">下表介绍 BTAD_InstallMode 可能的值。</span><span class="sxs-lookup"><span data-stu-id="9ca99-105">The following table describes the possible values for BTAD_InstallMode.</span></span>  
  
|<span data-ttu-id="9ca99-106">值</span><span class="sxs-lookup"><span data-stu-id="9ca99-106">Value</span></span>|<span data-ttu-id="9ca99-107">Description</span><span class="sxs-lookup"><span data-stu-id="9ca99-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ca99-108">Install</span><span class="sxs-lookup"><span data-stu-id="9ca99-108">Install</span></span>|<span data-ttu-id="9ca99-109">创建或更新到 BizTalkHostInstance （本地计算机）</span><span class="sxs-lookup"><span data-stu-id="9ca99-109">Create or update to BizTalkHostInstance (the local computer)</span></span>|  
|<span data-ttu-id="9ca99-110">导入</span><span class="sxs-lookup"><span data-stu-id="9ca99-110">Import</span></span>|<span data-ttu-id="9ca99-111">创建或更新到 ConfigurationDb （BizTalk 管理组的数据库）</span><span class="sxs-lookup"><span data-stu-id="9ca99-111">Create or update to ConfigurationDb (the BizTalk Management database for the group)</span></span>|  
|<span data-ttu-id="9ca99-112">Uninstall</span><span class="sxs-lookup"><span data-stu-id="9ca99-112">Uninstall</span></span>|<span data-ttu-id="9ca99-113">删除从 BizTalkHostInstance （本地计算机）</span><span class="sxs-lookup"><span data-stu-id="9ca99-113">Delete from BizTalkHostInstance (the local computer)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ca99-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ca99-114">See Also</span></span>  
 <span data-ttu-id="9ca99-115">[前期和后期处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="9ca99-115">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="9ca99-116">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="9ca99-116">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)