---
title: 属性错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d297db1a-352c-4e5a-b0aa-6edae8d74824
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2576fd336de135962d63a7c76b589671ba85faaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398515"
---
# <a name="properties-errors"></a><span data-ttu-id="1ea33-102">属性错误</span><span class="sxs-lookup"><span data-stu-id="1ea33-102">Properties Errors</span></span>
<span data-ttu-id="1ea33-103">本部分包含有关诊断和解决 WCF 属性错误的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="1ea33-103">This section contains detailed information for diagnosing and resolving WCF Properties errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ea33-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ea33-104">In This Section</span></span>  
  
-   [<span data-ttu-id="1ea33-105">加载属性时出错</span><span class="sxs-lookup"><span data-stu-id="1ea33-105">Error loading properties</span></span>](../core/error-loading-properties.md)  
  
-   [<span data-ttu-id="1ea33-106">保存属性时出错</span><span class="sxs-lookup"><span data-stu-id="1ea33-106">Error saving properties</span></span>](../core/error-saving-properties.md)  
  
-   [<span data-ttu-id="1ea33-107">项目位置无效</span><span class="sxs-lookup"><span data-stu-id="1ea33-107">Invalid project location</span></span>](../core/invalid-project-location.md)  
  
-   [<span data-ttu-id="1ea33-108">消息部分元素缺失</span><span class="sxs-lookup"><span data-stu-id="1ea33-108">Message part missing element</span></span>](../core/message-part-missing-element.md)  
  
-   [<span data-ttu-id="1ea33-109">不支持没有消息部分的消息类型</span><span class="sxs-lookup"><span data-stu-id="1ea33-109">Message types without parts are not supported</span></span>](../core/message-types-without-parts-are-not-supported.md)  
  
-   [<span data-ttu-id="1ea33-110">OutboundCustomHeaders 的格式不正确</span><span class="sxs-lookup"><span data-stu-id="1ea33-110">OutboundCustomHeaders does not have correct format</span></span>](../core/outboundcustomheaders-does-not-have-correct-format.md)  
  
-   [<span data-ttu-id="1ea33-111">项目位置不为空</span><span class="sxs-lookup"><span data-stu-id="1ea33-111">The project location is not empty</span></span>](../core/the-project-location-is-not-empty.md)  
  
-   [<span data-ttu-id="1ea33-112">无法从 XML 配置创建终结点行为配置元素</span><span class="sxs-lookup"><span data-stu-id="1ea33-112">Unable to create endpoint behavior configuration element from XML configuration</span></span>](../core/unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="1ea33-113">无法从 XML 配置创建服务行为配置元素</span><span class="sxs-lookup"><span data-stu-id="1ea33-113">Unable to create service behavior configuration element from XML configuration</span></span>](../core/unable-to-create-service-behavior-configuration-element-from-xml-configuration.md)  
  
-   [<span data-ttu-id="1ea33-114">无法导出客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="1ea33-114">Unable to export client endpoint configuration</span></span>](../core/unable-to-export-client-endpoint-configuration.md)  
  
-   [<span data-ttu-id="1ea33-115">无法导出服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="1ea33-115">Unable to export service endpoint configuration</span></span>](../core/unable-to-export-service-endpoint-configuration.md)  
  
-   [<span data-ttu-id="1ea33-116">找不到入站正文路径表达式的内容</span><span class="sxs-lookup"><span data-stu-id="1ea33-116">Unable to find content for inbound body path expression</span></span>](../core/unable-to-find-content-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="1ea33-117">找不到入站主体路径表达式的匹配项</span><span class="sxs-lookup"><span data-stu-id="1ea33-117">Unable to find match for inbound body path expression</span></span>](../core/unable-to-find-match-for-inbound-body-path-expression.md)  
  
-   [<span data-ttu-id="1ea33-118">意外的根元素</span><span class="sxs-lookup"><span data-stu-id="1ea33-118">Unexpected root element</span></span>](../core/unexpected-root-element.md)  
  
-   [<span data-ttu-id="1ea33-119">无法识别的出站消息封送类型</span><span class="sxs-lookup"><span data-stu-id="1ea33-119">Unrecognized outbound message marshalling type</span></span>](../core/unrecognized-outbound-message-marshalling-type.md)  
  
-   [<span data-ttu-id="1ea33-120">不支持的安全算法套件</span><span class="sxs-lookup"><span data-stu-id="1ea33-120">Unsupported security algorithm suite</span></span>](../core/unsupported-security-algorithm-suite.md)  
  
-   [<span data-ttu-id="1ea33-121">不支持的事务协议</span><span class="sxs-lookup"><span data-stu-id="1ea33-121">Unsupported transaction protocol</span></span>](../core/unsupported-transaction-protocol.md)  
  
-   [<span data-ttu-id="1ea33-122">WCF 客户端必须允许模拟以使用单一登录</span><span class="sxs-lookup"><span data-stu-id="1ea33-122">WCF client must allow impersonation to use Single Sign-On</span></span>](../core/wcf-client-must-allow-impersonation-to-use-single-sign-on.md)  
  
-   [<span data-ttu-id="1ea33-123">可能未安装 Windows 组件</span><span class="sxs-lookup"><span data-stu-id="1ea33-123">Windows components may not be installed</span></span>](../core/windows-components-may-not-be-installed.md)