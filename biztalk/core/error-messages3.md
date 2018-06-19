---
title: 错误 Messages3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1b9dd41280593de1472cd6af57ae8d1eb9fc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241773"
---
# <a name="error-messages"></a><span data-ttu-id="74733-102">错误消息</span><span class="sxs-lookup"><span data-stu-id="74733-102">Error Messages</span></span>
<span data-ttu-id="74733-103">下表列出了 PeopleSoft Enterprise 系统的组件接口中的错误消息及其描述，以及可能的更正方法。</span><span class="sxs-lookup"><span data-stu-id="74733-103">The following table lists error messages in the PeopleSoft Enterprise system's component interfaces, their descriptions, and possible corrections.</span></span>  
  
 <span data-ttu-id="74733-104">**错误消息**</span><span class="sxs-lookup"><span data-stu-id="74733-104">**Error messages**</span></span>  
  
|<span data-ttu-id="74733-105">错误 ID</span><span class="sxs-lookup"><span data-stu-id="74733-105">Error ID</span></span>|<span data-ttu-id="74733-106">可能的原因 / 错误说明</span><span class="sxs-lookup"><span data-stu-id="74733-106">Possible Cause / Error Description</span></span>|<span data-ttu-id="74733-107">可能的更正</span><span class="sxs-lookup"><span data-stu-id="74733-107">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="74733-108">E JNI0004</span><span class="sxs-lookup"><span data-stu-id="74733-108">E-JNI0004</span></span>|<span data-ttu-id="74733-109">没有 psjoa.jar。</span><span class="sxs-lookup"><span data-stu-id="74733-109">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="74733-110">出现 Java 异常。</span><span class="sxs-lookup"><span data-stu-id="74733-110">A Java exception occurred.</span></span>|<span data-ttu-id="74733-111">验证 PeopleSoft psjoa.jar 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="74733-111">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="74733-112">E PSFT0030</span><span class="sxs-lookup"><span data-stu-id="74733-112">E-PSFT0030</span></span>|<span data-ttu-id="74733-113">没有 psjoa.jar。</span><span class="sxs-lookup"><span data-stu-id="74733-113">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="74733-114">实例化组件接口 Bean 失败。</span><span class="sxs-lookup"><span data-stu-id="74733-114">Failed to instantiate Component Interface Beans.</span></span>|<span data-ttu-id="74733-115">验证 PeopleSoft psjoa.jar 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="74733-115">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="74733-116">E PSFT0019</span><span class="sxs-lookup"><span data-stu-id="74733-116">E-PSFT0019</span></span>|<span data-ttu-id="74733-117">错误的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="74733-117">Wrong server name.</span></span><br /><br /> <span data-ttu-id="74733-118">连接到 PeopleSoft 应用程序服务器失败。</span><span class="sxs-lookup"><span data-stu-id="74733-118">Connection to PeopleSoft Application Server failed.</span></span>|<span data-ttu-id="74733-119">验证 PeopleSoft 主机和用户参数。</span><span class="sxs-lookup"><span data-stu-id="74733-119">Verify PeopleSoft host and user parameters.</span></span>|  
|<span data-ttu-id="74733-120">E PSFT0024</span><span class="sxs-lookup"><span data-stu-id="74733-120">E-PSFT0024</span></span>|<span data-ttu-id="74733-121">错误的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="74733-121">Wrong user name and password.</span></span><br /><br /> <span data-ttu-id="74733-122">连接失败。</span><span class="sxs-lookup"><span data-stu-id="74733-122">Connection failed.</span></span> <span data-ttu-id="74733-123">错误消息： JavaClient 是无效的用户名称，或键入的密码错误。</span><span class="sxs-lookup"><span data-stu-id="74733-123">Error Message: JavaClient is an Invalid User name, or you typed the wrong password.</span></span>|<span data-ttu-id="74733-124">必须输入 PeopleSoft 用户名和密码，并且区分大小写。</span><span class="sxs-lookup"><span data-stu-id="74733-124">PeopleSoft user name and password are required and are case sensitive.</span></span> <span data-ttu-id="74733-125">确保输入信息时使用正确的大小写形式。</span><span class="sxs-lookup"><span data-stu-id="74733-125">Make sure that you are entering the information in the correct upper and lower cases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74733-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74733-126">See Also</span></span>  
 [<span data-ttu-id="74733-127">故障排除 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="74733-127">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)