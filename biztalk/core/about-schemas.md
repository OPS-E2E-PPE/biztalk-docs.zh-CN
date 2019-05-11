---
title: 有关架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ec2b79c-7cfe-4b00-bcff-dfad3944c83b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bda778473e1b2f79608650271ad3d250ed294cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362288"
---
# <a name="about-schemas"></a><span data-ttu-id="30b7a-102">有关架构</span><span class="sxs-lookup"><span data-stu-id="30b7a-102">About Schemas</span></span>
<span data-ttu-id="30b7a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 XML 架构定义 (XSD) 语言来定义所处理的所有消息的结构，并将这些消息结构定义称为架构。</span><span class="sxs-lookup"><span data-stu-id="30b7a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the XML Schema definition (XSD) language to define the structure of all messages that it processes, and refers to these definitions of message structure as schemas.</span></span> <span data-ttu-id="30b7a-104">除少数情况外，结构化消息是所有应用程序的核心。</span><span class="sxs-lookup"><span data-stu-id="30b7a-104">With few exceptions, structured messages are the core of any application.</span></span> <span data-ttu-id="30b7a-105">这些结构化消息可以采用任何形式（大型或小型），并面向一系列众多的后端系统和数据存储。</span><span class="sxs-lookup"><span data-stu-id="30b7a-105">These structured messages can take any form, large or small, and target a wide array of back-end systems and data stores.</span></span> <span data-ttu-id="30b7a-106">创建和使用结构化消息的系统通常使用不同的格式。</span><span class="sxs-lookup"><span data-stu-id="30b7a-106">Systems that create and consume the structured messages frequently use different formats.</span></span> <span data-ttu-id="30b7a-107">结构化消息的两种最常用的格式为 XML 和平面文件。</span><span class="sxs-lookup"><span data-stu-id="30b7a-107">Two of the most common formats for structured messages are XML and flat files.</span></span>  
  
 <span data-ttu-id="30b7a-108">BizTalk 编辑器设计用来对定义消息架构和验证特定消息是否符合该架构的过程进行简化。</span><span class="sxs-lookup"><span data-stu-id="30b7a-108">BizTalk Editor is designed to simplify the process of defining a message schema and validating whether a particular message conforms to that schema.</span></span> <span data-ttu-id="30b7a-109">在定义架构和验证消息的过程中，您可能需要执行以下一些任务：</span><span class="sxs-lookup"><span data-stu-id="30b7a-109">In the process of defining schemas and validating messages, you will likely perform some of the following tasks:</span></span>  
  
-   <span data-ttu-id="30b7a-110">为结构化 XML 消息创建架构。</span><span class="sxs-lookup"><span data-stu-id="30b7a-110">Create schemas for structured XML messages.</span></span>  
  
-   <span data-ttu-id="30b7a-111">为平面文件消息创建架构。</span><span class="sxs-lookup"><span data-stu-id="30b7a-111">Create schemas for flat file messages.</span></span>  
  
-   <span data-ttu-id="30b7a-112">从格式正确的 XML 实例数据生成架构。</span><span class="sxs-lookup"><span data-stu-id="30b7a-112">Generate schemas from well-formed XML instance data.</span></span>  
  
-   <span data-ttu-id="30b7a-113">验证消息是否符合特定架构。</span><span class="sxs-lookup"><span data-stu-id="30b7a-113">Validate message conformance to a specific schema.</span></span>  
  
-   <span data-ttu-id="30b7a-114">对架构执行设计时验证。</span><span class="sxs-lookup"><span data-stu-id="30b7a-114">Perform design-time validation of schemas.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30b7a-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="30b7a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="30b7a-116">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="30b7a-116">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)  
  
-   [<span data-ttu-id="30b7a-117">XSD 的角色</span><span class="sxs-lookup"><span data-stu-id="30b7a-117">Role of XSD</span></span>](../core/role-of-xsd.md)  
  
-   [<span data-ttu-id="30b7a-118">Web 上的 XSD 资源</span><span class="sxs-lookup"><span data-stu-id="30b7a-118">XSD Resources on the Web</span></span>](../core/xsd-resources-on-the-web.md)  
  
-   [<span data-ttu-id="30b7a-119">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="30b7a-119">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)  
  
-   [<span data-ttu-id="30b7a-120">使用其他架构的架构</span><span class="sxs-lookup"><span data-stu-id="30b7a-120">Schemas That Use Other Schemas</span></span>](../core/schemas-that-use-other-schemas.md)  
  
-   [<span data-ttu-id="30b7a-121">类型重用和派生</span><span class="sxs-lookup"><span data-stu-id="30b7a-121">Type Reuse and Derivations</span></span>](../core/type-reuse-and-derivations.md)  
  
-   [<span data-ttu-id="30b7a-122">从早期版本的 BizTalk Server 迁移架构</span><span class="sxs-lookup"><span data-stu-id="30b7a-122">Schema Migration from Previous Versions of BizTalk Server</span></span>](../core/schema-migration-from-previous-versions-of-biztalk-server.md)  
  
-   [<span data-ttu-id="30b7a-123">使用消息内容控制消息处理的方法</span><span class="sxs-lookup"><span data-stu-id="30b7a-123">Ways to Use Message Content to Control Message Processing</span></span>](../core/ways-to-use-message-content-to-control-message-processing.md)  
  
-   [<span data-ttu-id="30b7a-124">Visual Studio 中的架构验证</span><span class="sxs-lookup"><span data-stu-id="30b7a-124">Schema Validation in Visual Studio</span></span>](../core/schema-validation-in-visual-studio.md)  
  
-   [<span data-ttu-id="30b7a-125">实例消息的生成和验证</span><span class="sxs-lookup"><span data-stu-id="30b7a-125">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)