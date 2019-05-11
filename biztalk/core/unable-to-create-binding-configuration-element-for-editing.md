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
ms.openlocfilehash: c508f4839937315c64734f650fe84e87c60c0dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292878"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a><span data-ttu-id="8adb4-102">法创建要编辑的绑定配置元素</span><span class="sxs-lookup"><span data-stu-id="8adb4-102">Unable to create binding configuration element for editing</span></span>
## <a name="details"></a><span data-ttu-id="8adb4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8adb4-103">Details</span></span>  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8adb4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8adb4-104">Product Name</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="8adb4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8adb4-105">Product Version</span></span> |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    <span data-ttu-id="8adb4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8adb4-106">Event ID</span></span>     |                                                                  <span data-ttu-id="8adb4-107">0</span><span class="sxs-lookup"><span data-stu-id="8adb4-107">0</span></span>                                                                   |
|  <span data-ttu-id="8adb4-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8adb4-108">Event Source</span></span>   |                                                                  <span data-ttu-id="8adb4-109">0</span><span class="sxs-lookup"><span data-stu-id="8adb4-109">0</span></span>                                                                   |
|    <span data-ttu-id="8adb4-110">组件</span><span class="sxs-lookup"><span data-stu-id="8adb4-110">Component</span></span>    |                                                                  <span data-ttu-id="8adb4-111">0</span><span class="sxs-lookup"><span data-stu-id="8adb4-111">0</span></span>                                                                   |
|  <span data-ttu-id="8adb4-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8adb4-112">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="8adb4-113">0</span><span class="sxs-lookup"><span data-stu-id="8adb4-113">0</span></span>                                                                   |
|  <span data-ttu-id="8adb4-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="8adb4-114">Message Text</span></span>   | <span data-ttu-id="8adb4-115">无法创建绑定配置元素以进行编辑。</span><span class="sxs-lookup"><span data-stu-id="8adb4-115">Unable to create binding configuration element for editing.</span></span> <span data-ttu-id="8adb4-116">检查 BindingType 和 BindingConfiguration 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8adb4-116">Check the values of the BindingType and BindingConfiguration properties.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8adb4-117">解释</span><span class="sxs-lookup"><span data-stu-id="8adb4-117">Explanation</span></span>  
 <span data-ttu-id="8adb4-118">正在加载用户界面中显示的绑定元素时出错。</span><span class="sxs-lookup"><span data-stu-id="8adb4-118">There was an error loading a binding element for display in the user interface.</span></span> <span data-ttu-id="8adb4-119">此错误通常发生的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="8adb4-119">This error often occurs with custom binding.</span></span> <span data-ttu-id="8adb4-120">绑定元素可能已丢失的配置文件中，因此绑定下拉列表上可用。</span><span class="sxs-lookup"><span data-stu-id="8adb4-120">The binding element is probably missing in the configuration file and is therefore not available on the drop-down list for binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8adb4-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="8adb4-121">User Action</span></span>  
 <span data-ttu-id="8adb4-122">检查的值**BindingType**并**BindingConfiguration**属性。</span><span class="sxs-lookup"><span data-stu-id="8adb4-122">Check the values of the **BindingType** and **BindingConfiguration** properties.</span></span>  
  
 <span data-ttu-id="8adb4-123">创建绑定配置元素的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="8adb4-123">For further information on creating binding configuration elements, see the following resource:</span></span>  
  
-   [<span data-ttu-id="8adb4-124">配置 WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="8adb4-124">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)