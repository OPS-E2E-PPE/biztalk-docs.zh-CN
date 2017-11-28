---
title: "错误消息 1> |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a><span data-ttu-id="7d70d-102">错误消息</span><span class="sxs-lookup"><span data-stu-id="7d70d-102">Error Messages</span></span>
<span data-ttu-id="7d70d-103">下表介绍了 JD Edwards EnterpriseOne 系统中的错误消息，并提供了可能的更正。</span><span class="sxs-lookup"><span data-stu-id="7d70d-103">The following table describes error messages in the JD Edwards EnterpriseOne system and provides possible corrections for them.</span></span>  
  
|<span data-ttu-id="7d70d-104">错误 ID</span><span class="sxs-lookup"><span data-stu-id="7d70d-104">Error ID</span></span>|<span data-ttu-id="7d70d-105">可能的原因 / 错误说明</span><span class="sxs-lookup"><span data-stu-id="7d70d-105">Possible Cause / Error Description</span></span>|<span data-ttu-id="7d70d-106">可能的更正</span><span class="sxs-lookup"><span data-stu-id="7d70d-106">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="7d70d-107">E JDE0027</span><span class="sxs-lookup"><span data-stu-id="7d70d-107">E-JDE0027</span></span>|<span data-ttu-id="7d70d-108">缺少 JD Edwards EnterpriseOne JAR。</span><span class="sxs-lookup"><span data-stu-id="7d70d-108">JD Edwards EnterpriseOne JAR files missing.</span></span> <span data-ttu-id="7d70d-109">无法获取 JD Edwards EnterpriseOne 连接对象。</span><span class="sxs-lookup"><span data-stu-id="7d70d-109">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span>|<span data-ttu-id="7d70d-110">验证您的凭据。</span><span class="sxs-lookup"><span data-stu-id="7d70d-110">Verify your credentials.</span></span> <span data-ttu-id="7d70d-111">验证您的 CLASSPATH 设置和登录凭据。</span><span class="sxs-lookup"><span data-stu-id="7d70d-111">Verify your CLASSPATH settings and logon credentials.</span></span> <span data-ttu-id="7d70d-112">环境变量引用。</span><span class="sxs-lookup"><span data-stu-id="7d70d-112">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="7d70d-113">我 JDE0043</span><span class="sxs-lookup"><span data-stu-id="7d70d-113">I-JDE0043</span></span>|<span data-ttu-id="7d70d-114">错误配置文件，用户，密码的应用程序服务器、 端口、 环境、 路径。</span><span class="sxs-lookup"><span data-stu-id="7d70d-114">Wrong App Server, Port, Environment, Path for Configuration File, User, Password.</span></span> <span data-ttu-id="7d70d-115">登录失败。</span><span class="sxs-lookup"><span data-stu-id="7d70d-115">Log in failed.</span></span>|<span data-ttu-id="7d70d-116">验证您的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="7d70d-116">Verify your log in credentials.</span></span> <span data-ttu-id="7d70d-117">环境变量引用。</span><span class="sxs-lookup"><span data-stu-id="7d70d-117">Refer to Environment variable.</span></span>|  
|<span data-ttu-id="7d70d-118">我 JDE0048</span><span class="sxs-lookup"><span data-stu-id="7d70d-118">I-JDE0048</span></span>|<span data-ttu-id="7d70d-119">如果 jdearglist.txt 文件不存在或为空，当 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器打开时，会在登录中显示信息性消息。</span><span class="sxs-lookup"><span data-stu-id="7d70d-119">If the jdearglist.txt file does not exist or is empty, an informational message appears in the log when Microsoft BizTalk Adapter for JD Edwards EnterpriseOne opens.</span></span>|<span data-ttu-id="7d70d-120">更新 jdearglist.txt 文件以输入参数的列表，以便它们会自动右对齐，并因此，在左侧空白填充。</span><span class="sxs-lookup"><span data-stu-id="7d70d-120">Update the jdearglist.txt file to enter a list of parameters so that they are automatically right justified and padded on the left with blanks.</span></span> <span data-ttu-id="7d70d-121">有关详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="7d70d-121">For more information, see  [Handling String Values](../core/handling-string-values2.md).</span></span> <span data-ttu-id="7d70d-122">每次更改 jdearglist，你必须重新生成该业务对象的架构。</span><span class="sxs-lookup"><span data-stu-id="7d70d-122">Every time you change the jdearglist, you must regenerate the schemas for that business object.</span></span>|  
|<span data-ttu-id="7d70d-123">E JDE0027</span><span class="sxs-lookup"><span data-stu-id="7d70d-123">E-JDE0027</span></span>|<span data-ttu-id="7d70d-124">无法获取 JD Edwards EnterpriseOne 连接对象。</span><span class="sxs-lookup"><span data-stu-id="7d70d-124">Unable to acquire JD Edwards EnterpriseOne connection object.</span></span> <span data-ttu-id="7d70d-125">请检查您的 CLASSPATH 和凭据。</span><span class="sxs-lookup"><span data-stu-id="7d70d-125">Please check your CLASSPATH and credentials.</span></span>|<span data-ttu-id="7d70d-126">验证 jdeinterop.ini 的位置。</span><span class="sxs-lookup"><span data-stu-id="7d70d-126">Verify the location of jdeinterop.ini.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d70d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d70d-127">See Also</span></span>  
 <span data-ttu-id="7d70d-128">[故障排除博士 Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span><span class="sxs-lookup"><span data-stu-id="7d70d-128">[Troubleshooting JD Edwards EnterpriseOne](../core/troubleshooting-jd-edwards-enterpriseone.md) </span></span>  
 [<span data-ttu-id="7d70d-129">技术参考</span><span class="sxs-lookup"><span data-stu-id="7d70d-129">Technical Reference</span></span>](../core/technical-reference6.md)