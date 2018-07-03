---
title: 动态消息类型发现和架构解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5bbc5f8afaa8c08da04e9eab1b476e5884b2e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986406"
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>动态消息类型发现和架构解析
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]可实现动态消息类型发现和架构解析 SWIFT 反汇编程序和组装器中的。  
  
## <a name="swift-disassembler"></a>SWIFT 反汇编程序  
 SWIFT 反汇编程序 (DASM) 能够动态地发现收到的消息的消息类型和加载分析消息所需的相应架构。 此功能的最大的好处是，您可以配置单个管道使用 SWIFT 反汇编程序来处理任何 SWIFT 消息类型的 SWIFT 消息。 与本机 BizTalk 平面文件拆装器，不同 SWIFT 反汇编程序不需要生成单独的接收管道的 A4SWIFT 可能会遇到的每种消息类型。  
  
 如果您假设，在大多数情况下，系统收到的所有消息都将开头结构上同构的标头数据，可以使用动态消息类型发现。 标头内的数据是显示消息的消息类型的字段。 SWIFT 消息标头数据包含 SWIFT 消息块 1、 2 和 3，使用消息块 （称为应用程序标头） 的 2 中包含的类型信息。  
  
 SWIFT DASM 组件可以处理所有"单个"（非批处理） SWIFT 消息在初始状态而无需任何要设置的属性。 默认情况下，不设置 SWIFT 交换架构和 SWIFT 标头架构;但是，SWIFT DASM 组件将使用位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll SWIFT 标头架构来动态检测 SWIFT 消息类型和处理消息。 此外，BRE 和 XML 验证是默认情况下启用以便将完全验证处理任何消息。 SWIFT 标头架构属性设置为指向 RuntimeSchemas.dll 中的 SWIFT 标头还将导致与上面相同的行为。  
  
 当 SWIFT 反汇编程序 SWIFT 标头架构配置属性设置为"None"（默认值） 时，拆装器将动态解析和加载相应的架构，请执行以下步骤：  
  
1. 使用用户指定的标头架构 （由 SWIFT 标头架构配置属性指定） 来分析接收消息 （标头） 开头。  
  
2. A4SWIFT_MessageType 升级的属性字段中检查结果"标头 XML"。 如果不存在此字段，它使用字段的值作为"消息类型"，并继续执行步骤 4。 如果该字段不存在，则继续步骤 3。  
  
3. 检查 A4SWIFT_MessageType2 升级的属性字段的标头 XML （预计如果拆装器找不到 A4SWIFT_MessageType 字段）。 使用 A4SWIFT_MessageType2 字段值为"消息类型"。  
  
4. 如果在步骤 2 或 3 中标识的"消息类型"，"574"SWIFT 反汇编程序检查该消息类型"574"进行中 （这是拆装器的属性） 在双类型消息列表配置属性中指定的消息类型的列表。 如果是，它将继续到步骤 5。 如果不是，继续到步骤 6。  
  
5. 检查标头 XML A4SWIFT_SecondaryMessageType 升级的属性字段。 如果不存在此字段，拆装器使用字段的值 (例如，"IRSLST") 作为"消息的子类型"，并将其追加到的"消息类型"，例如，"574_IRSLST"。  
  
   > [!IMPORTANT]
   >  为步骤 5 的解释是简化的 SWIFT 反汇编程序实际作用以计算消息子类型。 实际上，SWIFT 反汇编程序将使用以下算法对以确定消息类型都有子类型，以及如果是这样，哪些的子类型，如下所示。  
  
   ```  
   Given MT type number nxx ...  
   if nxx is in the Dual-Type list {  
     if field 119 exists AND field 119 is NOT null/empty {  
       if n == 1 {  
         if field 119 == "STP" {  
           Use MTnxxPLUS schema  
         } else if field 119 == "REMIT" {  
           Use MTnxx schema  
         } else {  
           Use MTnxx_<field 119> schema  
         }   
       } else {  
         // n != 1  
         Use MTnxx_<field 119> schema  
       }  
     } else {  
       // field 119 does not exist or 119 does exist but is null/empty  
       Use MTnxx schema  
     }  
   } else {  
     // nxx is not a dual-type message  
     Use MTnxx schema  
   }  
   ```  
  
6. 拆装器现在知道消息类型，并且它可以通过连接命名前缀和后缀 （例如"MT"的前缀中以使"MT574_IRSLST") 一些固定的架构来形成交换架构名称。  
  
7. 将交换架构加载 （按名称），并将其整个消息**从头开始启动**，使用加载的架构 (这意味着，拆装器对标头数据两次： 一次使用的标头架构，并再次使用交换架构的开头）。 交换架构必须是可以解析出整个消息，包括标头。  
  
   > [!NOTE]
   >  拆装器可以使用所有 A4SWIFT SWIFT 消息架构来分析整个 SWIFT 交换 （SWIFT 块 1、 2、 3、 4 和 5）。 拆装器使用默认 SWIFT 标头架构分析块 1、 2 和 3 只。 有关详细信息，请参阅下面的内容。  
  
   上面所述的架构解析算法意味着，为了使动态消息类型发现正常工作，SWIFT 标头架构必须包含拆装器已提升使用以下升级的属性 （在 A4SWIFT 中定义的字段属性架构，Microsoft.Solutions.A4SWIFT.Property.PropertySchema）：  
  
- **A4SWIFT_MessageType**  
  
- **A4SWIFT_MessageType2** (可选如果**A4SWIFT_MessageTypes**使用)  
  
- **A4SWIFT_SecondaryMessageType** （可选）  
  
  有关这些及其他升级的属性的详细信息，请参阅[A4SWIFT_ * 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
> [!NOTE]
>  如果 SWIFT 标头架构设置为**无**，则应指定完整的交换架构**SWIFT 交换架构**属性。 在这种情况下，拆装器使用指定的交换架构分析 A4SWIFT 接收的所有消息。 也就是说，可以禁用动态架构解析和配置管道以接收其类型与指定的交换架构匹配的消息。  
  
 A4SWIFT 安装 SWIFT 标头默认架构 (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) 可以分析 SWIFT 标准标头数据并具有必要的升级的属性，以便动态架构解析。  
  
 默认 SWIFT 标头架构有以下升级的字段：  
  
- **可以忽略 SWIFTHeader/ApplicationHeaderBlock_Input MessageType**。 拆装器将其升级使用**A4SWIFT_MessageType**属性。  
  
- **可以忽略 SWIFTHeader/ApplicationHeaderBlock_Output MessageType**。 拆装器将其升级使用**A4SWIFT_MessageType2**属性。  
  
- **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**。 拆装器将其升级使用**A4SWIFT_MessageType**属性。  
  
  拆装器使用**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**作为标头架构如果 SWIFT 标头架构和 SWIFT 交换架构配置属性设置为默认情况下"None"。  
  
## <a name="swift-assembler"></a>SWIFT 汇编程序  
 SWIFT 反汇编程序，如 SWIFT 汇编程序具有动态发现出站消息的消息类型和加载相应的架构序列化消息所需的功能。 此功能，可配置 SWIFT 汇编程序用于处理任何 SWIFT 消息类型的 SWIFT 消息的单个管道。 与本机 BizTalk 平面文件组装器，不同 SWIFT 汇编程序不需要可构建 A4SWIFT 可能会遇到的每种消息类型的单独的发送管道。  
  
 SWIFT 汇编程序中的动态架构解析是比要简单得 SWIFT 反汇编程序中，因为组装器会恢复到 SWIFT 的平面文件格式序列化 XML 的作业。 XML 的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]给予 SWIFT 汇编程序，序列化包含 SWIFT 汇编程序可以使用直接加载适当架构，以进行序列化的消息类型和架构信息。 在这种情况下，SWIFT 汇编程序不具有任何可配置性对于标头和交换架构： 它始终使用指定的架构将进行序列化的 XML 中。  
  
## <a name="see-also"></a>请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)