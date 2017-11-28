---
title: "属性错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d297db1a-352c-4e5a-b0aa-6edae8d74824
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c03358ba08df939e7058a6d73603969dcddd8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="properties-errors"></a><span data-ttu-id="04736-102">属性错误</span><span class="sxs-lookup"><span data-stu-id="04736-102">Properties Errors</span></span>
<span data-ttu-id="04736-103">本部分包含有关诊断和解决 WCF 属性错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="04736-103">This section contains detailed information for diagnosing and resolving WCF Properties errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04736-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="04736-104">In This Section</span></span>  
  
-   [<span data-ttu-id="04736-105">错误加载属性</span><span class="sxs-lookup"><span data-stu-id="04736-105">Error loading properties</span></span>](../core/error-loading-properties.md)  
  
-   [<span data-ttu-id="04736-106">保存属性时出错</span><span class="sxs-lookup"><span data-stu-id="04736-106">Error saving properties</span></span>](../core/error-saving-properties.md)  
  
-   [<span data-ttu-id="04736-107">无效的项目位置</span><span class="sxs-lookup"><span data-stu-id="04736-107">Invalid project location</span></span>](../core/invalid-project-location.md)  
  
-   [<span data-ttu-id="04736-108">消息部分缺少元素</span><span class="sxs-lookup"><span data-stu-id="04736-108">Message part missing element</span></span>](../core/message-part-missing-element.md)  
  
-   [<span data-ttu-id="04736-109">不支持没有部分的消息类型</span><span class="sxs-lookup"><span data-stu-id="04736-109">Message types without parts are not supported</span></span>](../core/message-types-without-parts-are-not-supported.md)  
  
-   [<span data-ttu-id="04736-110">OutboundCustomHeaders 没有正确的格式</span><span class="sxs-lookup"><span data-stu-id="04736-110">OutboundCustomHeaders does not have correct format</span></span>](../core/outboundcustomheaders-does-not-have-correct-format.md)  
  
-   [<span data-ttu-id="04736-111">项目位置不为空</span><span class="sxs-lookup"><span data-stu-id="04736-111">The project location is not empty</span></span>](../core/the-project-location-is-not-empty.md)  
  
-   [<span data-ttu-id="04736-112">无法从 XML 配置创建终结点行为配置元素</span><span class="sxs-lookup"><span data-stu-id="04736-112">Unable to create endpoint behavior configuration element from XML configuration</span></span>](../core/unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="04736-113">无法从 XML 配置创建服务行为配置元素</span><span class="sxs-lookup"><span data-stu-id="04736-113">Unable to create service behavior configuration element from XML configuration</span></span>](../core/unable-to-create-service-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="04736-114">无法导出客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="04736-114">Unable to export client endpoint configuration</span></span>](../core/unable-to-export-client-endpoint-configuration.md)  
  
-   [<span data-ttu-id="04736-115">无法导出服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="04736-115">Unable to export service endpoint configuration</span></span>](../core/unable-to-export-service-endpoint-configuration.md)  
  
-   [<span data-ttu-id="04736-116">找不到入站的正文路径表达式的内容</span><span class="sxs-lookup"><span data-stu-id="04736-116">Unable to find content for inbound body path expression</span></span>](../core/unable-to-find-content-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="04736-117">找不到入站的正文路径表达式的匹配项</span><span class="sxs-lookup"><span data-stu-id="04736-117">Unable to find match for inbound body path expression</span></span>](../core/unable-to-find-match-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="04736-118">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="04736-118">Unexpected root element</span></span>](../core/unexpected-root-element.md)  
  
-   [<span data-ttu-id="04736-119">无法识别出站消息类型的封送处理</span><span class="sxs-lookup"><span data-stu-id="04736-119">Unrecognized outbound message marshalling type</span></span>](../core/unrecognized-outbound-message-marshalling-type.md)  
  
-   [<span data-ttu-id="04736-120">不支持的安全算法套件</span><span class="sxs-lookup"><span data-stu-id="04736-120">Unsupported security algorithm suite</span></span>](../core/unsupported-security-algorithm-suite.md)  
  
-   [<span data-ttu-id="04736-121">不受支持的事务处理协议</span><span class="sxs-lookup"><span data-stu-id="04736-121">Unsupported transaction protocol</span></span>](../core/unsupported-transaction-protocol.md)  
  
-   [<span data-ttu-id="04736-122">WCF 客户端必须允许的模拟，以便使用单一登录</span><span class="sxs-lookup"><span data-stu-id="04736-122">WCF client must allow impersonation to use Single Sign-On</span></span>](../core/wcf-client-must-allow-impersonation-to-use-single-sign-on.md)  
  
-   [<span data-ttu-id="04736-123">Windows 组件可能未安装</span><span class="sxs-lookup"><span data-stu-id="04736-123">Windows components may not be installed</span></span>](../core/windows-components-may-not-be-installed.md)