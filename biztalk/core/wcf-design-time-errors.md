---
title: WCF 设计时错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1327906a-6524-4937-830c-844d5fc81dc6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee67253478220a5fb018beb7ad27ae85eac7693e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399128"
---
# <a name="wcf-design-time--errors"></a><span data-ttu-id="4f72a-102">WCF 设计时错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-102">WCF Design-Time  Errors</span></span>
<span data-ttu-id="4f72a-103">本部分包含有关诊断和解决 WCF 设计时配置错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="4f72a-103">This section contains detailed information for diagnosing and resolving WCF design-time configuration errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f72a-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="4f72a-104">In This Section</span></span>  
  
-   [<span data-ttu-id="4f72a-105">操作错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-105">Action Errors</span></span>](../core/action-errors.md)  
  
-   [<span data-ttu-id="4f72a-106">地址错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-106">Address Errors</span></span>](../core/address-errors.md)  
  
-   [<span data-ttu-id="4f72a-107">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-107">Application Errors</span></span>](../core/application-errors.md)  
  
-   [<span data-ttu-id="4f72a-108">程序集错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-108">Assembly Errors</span></span>](../core/assembly-errors.md)  
  
-   [<span data-ttu-id="4f72a-109">绑定错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-109">Binding Errors</span></span>](../core/binding-errors.md)  
  
-   [<span data-ttu-id="4f72a-110">证书错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-110">Certificate Errors</span></span>](../core/certificate-errors.md)  
  
-   [<span data-ttu-id="4f72a-111">通信模式错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-111">Communication Pattern Errors</span></span>](../core/communication-pattern-errors.md)  
  
-   [<span data-ttu-id="4f72a-112">处理错误时出错</span><span class="sxs-lookup"><span data-stu-id="4f72a-112">Error Handling Errors</span></span>](../core/error-handling-errors.md)  
  
-   [<span data-ttu-id="4f72a-113">标识错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-113">Identity Errors</span></span>](../core/identity-errors.md)  
  
-   [<span data-ttu-id="4f72a-114">导入和导出错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-114">Import and Export Errors</span></span>](../core/import-and-export-errors.md)  
  
-   [<span data-ttu-id="4f72a-115">元数据错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-115">Metadata Errors</span></span>](../core/metadata-errors.md)  
  
-   [<span data-ttu-id="4f72a-116">名称错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-116">Name Errors</span></span>](../core/name-errors.md)  
  
-   [<span data-ttu-id="4f72a-117">端口配置错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-117">Port Configuration Errors</span></span>](../core/port-configuration-errors.md)  
  
-   [<span data-ttu-id="4f72a-118">属性错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-118">Properties Errors</span></span>](../core/properties-errors.md)  
  
-   [<span data-ttu-id="4f72a-119">接收错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-119">Receive Errors</span></span>](../core/receive-errors.md)  
  
-   [<span data-ttu-id="4f72a-120">注册表错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-120">Registry Errors</span></span>](../core/registry-errors.md)  
  
-   [<span data-ttu-id="4f72a-121">方案错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-121">Scheme Errors</span></span>](../core/scheme-errors.md)  
  
-   [<span data-ttu-id="4f72a-122">发送错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-122">Send Errors</span></span>](../core/send-errors.md)  
  
-   [<span data-ttu-id="4f72a-123">模板错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-123">Template Errors</span></span>](../core/template-errors.md)  
  
-   [<span data-ttu-id="4f72a-124">超时错误</span><span class="sxs-lookup"><span data-stu-id="4f72a-124">Timeout Errors</span></span>](../core/timeout-errors.md)