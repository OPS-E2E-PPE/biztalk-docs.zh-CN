---
title: BTAD_InstallMode | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_InstallMode [environment variable]
ms.assetid: b0ca48b8-c672-4704-9a04-2c6f159e57be
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94b86412d081602ab77330bb4a6b6e567d662d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357822"
---
# <a name="btadinstallmode"></a><span data-ttu-id="dacd3-102">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="dacd3-102">BTAD_InstallMode</span></span>
<span data-ttu-id="dacd3-103">BTAD_InstallMode 介绍 BizTalk 应用程序部署的安装模式。</span><span class="sxs-lookup"><span data-stu-id="dacd3-103">BTAD_InstallMode describes the installation mode for BizTalk application deployment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dacd3-104">备注</span><span class="sxs-lookup"><span data-stu-id="dacd3-104">Remarks</span></span>  
 <span data-ttu-id="dacd3-105">下表介绍 BTAD_InstallMode 可能的值。</span><span class="sxs-lookup"><span data-stu-id="dacd3-105">The following table describes the possible values for BTAD_InstallMode.</span></span>  
  
|<span data-ttu-id="dacd3-106">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="dacd3-106">Value</span></span>|<span data-ttu-id="dacd3-107">Description</span><span class="sxs-lookup"><span data-stu-id="dacd3-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dacd3-108">安装</span><span class="sxs-lookup"><span data-stu-id="dacd3-108">Install</span></span>|<span data-ttu-id="dacd3-109">创建或更新到 BizTalkHostInstance （本地计算机）</span><span class="sxs-lookup"><span data-stu-id="dacd3-109">Create or update to BizTalkHostInstance (the local computer)</span></span>|  
|<span data-ttu-id="dacd3-110">导入</span><span class="sxs-lookup"><span data-stu-id="dacd3-110">Import</span></span>|<span data-ttu-id="dacd3-111">创建或更新到 ConfigurationDb （组的 BizTalk 管理数据库）</span><span class="sxs-lookup"><span data-stu-id="dacd3-111">Create or update to ConfigurationDb (the BizTalk Management database for the group)</span></span>|  
|<span data-ttu-id="dacd3-112">Uninstall</span><span class="sxs-lookup"><span data-stu-id="dacd3-112">Uninstall</span></span>|<span data-ttu-id="dacd3-113">删除从 BizTalkHostInstance （本地计算机）</span><span class="sxs-lookup"><span data-stu-id="dacd3-113">Delete from BizTalkHostInstance (the local computer)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dacd3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="dacd3-114">See Also</span></span>  
 <span data-ttu-id="dacd3-115">[预处理和后处理脚本环境变量](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="dacd3-115">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="dacd3-116">环境变量如何指示部署状态</span><span class="sxs-lookup"><span data-stu-id="dacd3-116">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)