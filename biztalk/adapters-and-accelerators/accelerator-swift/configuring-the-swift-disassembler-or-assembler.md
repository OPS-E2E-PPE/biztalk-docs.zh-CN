---
title: 配置 SWIFT 反汇编程序或汇编程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8920a8b74da14eeb8186d153444ced7c54d57724
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005062"
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a><span data-ttu-id="2a5c5-102">配置 SWIFT 反汇编程序或汇编程序</span><span class="sxs-lookup"><span data-stu-id="2a5c5-102">Configuring the SWIFT Disassembler or Assembler</span></span>
<span data-ttu-id="2a5c5-103">SWIFT 反汇编程序或 SWIFT 汇编程序添加自定义管道后，你必须将其配置为提供 （如启用/禁用动态消息类型发现、 入站 debatching、 XML 验证，在特定方案所需的功能业务规则引擎 (BRE) 验证和等等）。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-103">After you add the SWIFT disassembler or SWIFT assembler to a custom pipeline, you must configure it to provide the functionality you want for the particular scenario (such as enabling/disabling dynamic message type discovery, inbound debatching, XML validation, Business Rule Engine (BRE) validation, and so on).</span></span> <span data-ttu-id="2a5c5-104">必须在开发期间编译和部署自定义调用它们的管道之前配置的 SWIFT 反汇编程序和汇编程序。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-104">You must configure the SWIFT disassembler and assembler during development time before you compile and deploy the custom pipelines that invoke them.</span></span> <span data-ttu-id="2a5c5-105">若要配置 SWIFT 反汇编程序汇编程序，在管道设计器中选择的组件和编辑属性窗口中的配置属性。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-105">To configure the SWIFT disassembler/assembler, select the component in Pipeline Designer and edit the configuration properties in the Properties window.</span></span>  
  
 <span data-ttu-id="2a5c5-106">请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)完整的详细信息和每个配置属性，以及其他使用情况和配置信息的说明。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-106">Refer to [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) for complete details and descriptions for each configuration property, as well as other usage and configuration information.</span></span>  
  
 <span data-ttu-id="2a5c5-107">请参阅[SWIFT 汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)完整的详细信息和说明的编码字符集配置属性，以及其他使用情况和配置信息。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-107">Refer to [SWIFT Assembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) for complete details and descriptions for the Encoding Charset configuration property, as well as other usage and configuration information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a5c5-108">配置、 编译和部署自定义管道后，配置中的更改需要重新编译和重新部署自定义的管道。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-108">After you configure, compile, and deploy the custom pipelines, changes in configuration will require re-compiling and re-deployment of the custom pipelines.</span></span>  
  
 <span data-ttu-id="2a5c5-109">配置、 编译和部署自定义管道处理 SWIFT 消息后，你可以设置最多接收位置的使用自定义 SWIFT 接收管道，和发送端口使用自定义 SWIFT 发送管道。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-109">After you configure, compile, and deploy your custom pipelines for processing SWIFT messages, you can set up receive locations that use your custom SWIFT receive pipeline, and send ports that use your custom SWIFT send pipeline.</span></span> <span data-ttu-id="2a5c5-110">接收端口的有关部署管道和配置的详细信息，接收位置，并发送端口，请参阅[模块 4： 创建 XML 接收和平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)，[模块 5： 创建接收平面文件和XML 发送端口](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)，和 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="2a5c5-110">For more information about deploying pipelines and configuring receive ports, receive locations, and send ports, see [Module 4: Creating XML Receive and Flat File Send Ports](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [Module 5: Creating Flat File Receive and XML Send Ports](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md), and BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="2a5c5-111">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="2a5c5-111">This section contains:</span></span>  
  
-   [<span data-ttu-id="2a5c5-112">配置 SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="2a5c5-112">Configuring the SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [<span data-ttu-id="2a5c5-113">配置 SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="2a5c5-113">Configuring the SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a5c5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a5c5-114">See Also</span></span>  
 [<span data-ttu-id="2a5c5-115">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="2a5c5-115">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)