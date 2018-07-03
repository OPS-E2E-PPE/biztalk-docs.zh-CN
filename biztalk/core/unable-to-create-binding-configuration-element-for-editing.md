---
title: 无法创建绑定配置元素以进行编辑 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71853662-5a4a-417e-8160-c93dbcbea336
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e58ec9966d0e0534d078fc5741f267bf02e735
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974334"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="55852-102">法创建要编辑的绑定配置元素</span><span class="sxs-lookup"><span data-stu-id="55852-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="55852-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="55852-103">Details</span></span>  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="55852-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="55852-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="55852-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="55852-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    <span data-ttu-id="55852-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="55852-106">Event ID</span></span>     |                                                                  <span data-ttu-id="55852-107">0</span><span class="sxs-lookup"><span data-stu-id="55852-107">0</span></span>                                                                   |
|  <span data-ttu-id="55852-108">事件源</span><span class="sxs-lookup"><span data-stu-id="55852-108">Event Source</span></span>   |                                                                  <span data-ttu-id="55852-109">0</span><span class="sxs-lookup"><span data-stu-id="55852-109">0</span></span>                                                                   |
|    <span data-ttu-id="55852-110">组件</span><span class="sxs-lookup"><span data-stu-id="55852-110">Component</span></span>    |                                                                  <span data-ttu-id="55852-111">0</span><span class="sxs-lookup"><span data-stu-id="55852-111">0</span></span>                                                                   |
|  <span data-ttu-id="55852-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="55852-112">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="55852-113">0</span><span class="sxs-lookup"><span data-stu-id="55852-113">0</span></span>                                                                   |
|  <span data-ttu-id="55852-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="55852-114">Message Text</span></span>   | <span data-ttu-id="55852-115">无法创建绑定配置元素以进行编辑。</span><span class="sxs-lookup"><span data-stu-id="55852-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="55852-116">检查 BindingType 和 BindingConfiguration 属性的值。</span><span class="sxs-lookup"><span data-stu-id="55852-116">Check the values of the BindingType and BindingConfiguration properties.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="55852-117">解释</span><span class="sxs-lookup"><span data-stu-id="55852-117">Explanation</span></span>  
 <span data-ttu-id="55852-118">加载绑定元素以显示在用户界面中时出错。</span><span class="sxs-lookup"><span data-stu-id="55852-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="55852-119">此错误通常发生在自定义绑定中。</span><span class="sxs-lookup"><span data-stu-id="55852-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="55852-120">配置文件中的绑定元素可能已丢失，因此绑定下拉列表中没有该元素。</span><span class="sxs-lookup"><span data-stu-id="55852-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55852-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="55852-121">User Action</span></span>  
 <span data-ttu-id="55852-122">检查的值**BindingType**并**BindingConfiguration**属性。</span><span class="sxs-lookup"><span data-stu-id="55852-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="55852-123">有关创建绑定配置元素的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="55852-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="55852-124">配置 WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="55852-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)