---
title: 动态消息类型发现和架构解决 |Microsoft 文档
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
ms.openlocfilehash: 77e9a8949787fcd3c7e942c406c9f31470894a8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211333"
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a>动态消息类型发现和架构解决
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]使您可以动态消息类型发现和架构解决 SWIFT 反汇编程序和汇编程序中的。  
  
## <a name="swift-disassembler"></a>SWIFT 反汇编程序  
 SWIFT 反汇编程序 (DASM) 能够动态发现收到的消息的消息类型和加载分析消息所需的相应架构。 此功能的最大优点是，你可以配置单个管道 SWIFT 反汇编程序用于处理 SWIFT 消息的任何 SWIFT 消息类型。 与本机 BizTalk 平面文件反汇编程序，不同 SWIFT 反汇编程序不需要生成用于 A4SWIFT 可能会遇到每种消息类型的单独接收管道。  
  
 当你假定，在大多数情况下，系统将接收的所有消息都将以开头结构上同类标头数据，你可以使用动态消息类型发现。 标头内数据是显示消息的消息类型的字段。 对于 SWIFT 消息，标头数据包含 SWIFT 消息块 1、 2 和 3，使用消息块 2 （称为应用程序标头） 中包含的类型信息。  
  
 SWIFT DASM 组件可以处理所有"单个"（非批处理） SWIFT 消息现成而无需任何要设置的属性。 默认情况下，不设置 SWIFT 交换架构和 SWIFT 标头架构;但是，SWIFT DASM 组件将使用 SWIFT 标头架构 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 中存在动态检测 SWIFT 消息类型和处理消息。 此外，BRE 和 XML 验证是默认启用以便将完全验证任何所处理的消息。 将 SWIFT 标头架构属性设置为指向 RuntimeSchemas.dll SWIFT 标头还将导致与上面相同的操作。  
  
 当 SWIFT 反汇编程序 SWIFT 标头架构配置属性设置为"None"（默认值） 时，拆装器动态解析并加载相应的架构，通过执行以下步骤：  
  
1.  使用用户指定的标头架构 （由 SWIFT 标头架构配置属性指定） 来分析接收消息的开头 （标头中）。  
  
2.  为 A4SWIFT_MessageType 提升的属性字段检查结果"标头 XML"。 如果不存在此字段，它将作为"消息类型"中使用的字段值，将转到步骤 4。 如果该字段不存在，则继续步骤 3。  
  
3.  检查 A4SWIFT_MessageType2 提升的属性字段的标头 XML （预期如果拆装器找不到 A4SWIFT_MessageType 字段）。 使用作为"消息类型"A4SWIFT_MessageType2 字段值。  
  
4.  如果在步骤 2 或 3 中标识的"消息类型"，"574"SWIFT 拆装器检查消息类型"574"是否在双类型消息列表配置属性 （这是一个属性反汇编程序） 中指定的消息类型的列表。 如果是，它将转到步骤 5。 如果不是，将转到步骤 6。  
  
5.  检查标头 XML A4SWIFT_SecondaryMessageType 提升的属性字段。 如果不存在此字段，拆装器使用的"消息的子类型"的字段值 (例如，"IRSLST")，并将其追加到的"消息类型"，例如，"574_IRSLST"。  
  
    > [!IMPORTANT]
    >  步骤 5 为提供的说明是什么 SWIFT 反汇编程序的实际作用以计算消息子类型的简化形式。 事实上，SWIFT 反汇编程序将使用以下算法对以确定消息类型都有子类型，以及如果是这样，哪些的子类型，如下所示。  
  
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
  
6.  反汇编程序现在就知道消息类型，同时它可以通过串联命名前缀和后缀 （例如"MT"的前缀中以使"MT574_IRSLST") 一些固定的架构形成交换架构名称。  
  
7.  载入交换架构 （按名称），并将整个消息，**从头开始**，使用加载的架构 (这意味着，拆装器分析的标头数据两次： 一次使用的标头架构，并再次使用交换架构开头）。 交换架构必须能够分析整个消息，包括标头。  
  
    > [!NOTE]
    >  反汇编程序可以使用所有 A4SWIFT SWIFT 消息架构来分析整个 SWIFT 交换 （SWIFT 块 1、 2、 3、 4 和 5）。 反汇编程序使用默认 SWIFT 标头架构来分析块 1、 2 和 3 仅。 有关详细信息，请参阅下面的内容。  
  
 上面所述的架构解析算法意味着，在动态消息类型发现正常工作的顺序，SWIFT 标头架构必须包含拆装器已提升使用以下提升的属性 （在 A4SWIFT 中定义的字段属性架构中，是 Microsoft.Solutions.A4SWIFT.Property.PropertySchema）：  
  
-   **A4SWIFT_MessageType**  
  
-   **A4SWIFT_MessageType2** (可选如果**A4SWIFT_MessageTypes**使用)  
  
-   **A4SWIFT_SecondaryMessageType** （可选）  
  
 有关这些及其他提升的属性的详细信息，请参阅[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。  
  
> [!NOTE]
>  如果 SWIFT 标头架构设置为**无**，您应指定完成交换架构**SWIFT 交换架构**属性。 在这种情况下，拆装器使用指定的交换架构分析 A4SWIFT 接收的所有消息。 即，禁用动态架构解析，并配置要只接收的消息其类型与指定的交换架构匹配的管线。  
  
 A4SWIFT 安装的默认 SWIFT 标头架构 (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) 可以分析 SWIFT 标准标头数据，并具有必要的提升的属性，这有助于动态架构解决。  
  
 默认 SWIFT 标头架构具有以下提升的字段：  
  
-   **可以忽略 SWIFTHeader/ApplicationHeaderBlock_Input MessageType**。 反汇编程序提升这使用**A4SWIFT_MessageType**属性。  
  
-   **可以忽略 SWIFTHeader/ApplicationHeaderBlock_Output MessageType**。 反汇编程序提升这使用**A4SWIFT_MessageType2**属性。  
  
-   **SWIFTHeader/UserHeaderBlock/ValidationFlag_119**。 反汇编程序提升这使用**A4SWIFT_MessageType**属性。  
  
 反汇编程序使用**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**默认情况下，作为标头架构如果 SWIFT 标头架构和 SWIFT 交换架构配置属性设置为"None"。  
  
## <a name="swift-assembler"></a>SWIFT 汇编程序  
 SWIFT 反汇编程序，如 SWIFT 汇编程序有能够动态发现出站消息的消息类型和加载序列化消息所需的相应架构。 此功能可以配置单个管道使用 SWIFT 汇编程序处理 SWIFT 消息的任何 SWIFT 消息类型。 与不同的本机 BizTalk 平面文件汇编，SWIFT 汇编程序不需要你可以构建用于 A4SWIFT 可能会遇到每种消息类型的单独发送管道。  
  
 在 SWIFT 汇编程序动态架构解析是比要简单得 SWIFT 反汇编程序中，因为汇编程序表现回 SWIFT 平面文件格式序列化为 XML。 XML，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]赋予 SWIFT 汇编程序，序列化包含 SWIFT 汇编程序可用于直接加载序列化的相应架构的消息类型和架构信息。 在这种情况下，SWIFT 汇编程序没有标头和交换架构任何可配置性： 它始终使用指定的架构中将进行序列化的 XML。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SWIFT 反汇编程序和汇编程序](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)