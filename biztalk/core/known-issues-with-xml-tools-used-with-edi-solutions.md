---
title: 使用 XML 工具与 EDI 解决方案一起使用的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d9b361-be98-494c-b32d-03892672fef1
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46114bc6afdf4ed1f834dfe974439222b98ac9b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329954"
---
# <a name="known-issues-with-xml-tools-used-with-edi-solutions"></a>XML 工具与 EDI 解决方案一起使用的已知的问题
本主题介绍在 BizTalk Server 中的 XML 工具的已知的问题。  
  
## <a name="validation-of-test-map-input-and-output-file-still-occurs-when-the-validate-property-is-set-to-false"></a>验证测试映射输入和输出文件仍会发生时验证属性设置为 False  
 如果将测试映射输入属性设置为与测试映射**本机**和验证测试映射输入和验证测试映射输出属性设置为**False**，仍会执行验证。 这是因为本机格式输入的文件将转换为 XML 格式，并且 BizTalk Server 将验证针对该架构的 XML。 如果在输入文件中有验证问题，此验证机制将发布错误，即使验证测试映射输入和验证测试映射输出属性设置为**False**。  
  
## <a name="length-validation-is-not-performed-on-a-data-element-in-a-generated-instance-that-is-pulled-from-an-enum-list-in-the-schema"></a>对于从架构中的枚举列表请求生成的实例中的数据元素长度验证不会执行  
 当从架构生成一个实例，并在架构中的数据元素的枚举值不满足长度要求时，该实例可能会生成与随后将 XSD 验证失败由于长度要求的数据元素。 架构验证不会检查从架构中的枚举列表提取生成的实例中的值是否满足最小/最大长度要求。  
  
## <a name="validate-schema-may-not-detect-an-invalid-transaction-set-id-code"></a>验证架构可能检测不到无效的事务集 ID 代码  
 当您使用验证架构中的解决方案资源管理器窗口的验证架构命令[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，检查根节点可能检测不到根引用节点的最后部分中的无效事务集 ID 代码 (格式 X12_\<版本号\>_TSID)。 如果架构的根引用节点中的 TSID 是无效的但它与架构中 ST01 元素的枚举节点中的 TSID 相同，则验证架构操作将不会检测该 TSID 是无效。  
  
## <a name="visual-studio-must-be-restarted-to-make-an-enum-change-in-a-schema-effective-for-instance-validation"></a>必须重新启动 visual Studio，以使更改生效的架构中对实例验证枚举  
 如果你更改架构中的枚举列表中，保存该架构，然后运行实例验证，BizTalk Server 将执行验证基于架构，而不是最新版本的上一版本。 BizTalk Server 将不使用架构的最新版本，直到重新启动 Visual Studio。  
  
## <a name="the-edi-instance-properties-dialog-box-may-be-displayed-when-not-needed-in-the-testmap-operation"></a>不需要在测试映射操作中时，可能会显示 EDI 实例属性对话框  
 BizTalk Server 将显示 EDI 实例属性对话框，在测试映射过程中两次： 一次，以便您可以输入解释输入的消息实例，一次用于输入分隔符以生成输出消息所必需的分隔符实例。 BizTalk Server 应显示 EDI 实例属性对话框中，两次并仅对 EDI 架构;但是，BizTalk Server 可能显示对话框针对非 EDI 架构和多个只需两次。 如果是这样，关闭对话框。  
  
## <a name="validation-of-an-xml-preserved-interchange-is-not-supported"></a>不支持验证 XML 保留交换  
 验证保留的交换时，如果您选择的 XML 时**验证实例输入类型**属性，则操作将失败且不会返回。 但是，如果您选择**本机**有关**验证实例输入类型**时验证保留的交换，操作将成功。  
  
## <a name="an-instance-generated-for-a-hipaa-278-schema-will-contain-both-request-and-response-sections"></a>实例生成为 HIPAA 278 架构将同时包含请求和响应部分  
 HIPAA 278 架构用于 278 请求和 278 响应消息。 如果您在 278 架构上使用生成实例命令，生成的实例将包含请求和响应部分，应永远不会发送。 若要创建可操作的 278 请求或 278 响应消息，请打开在文本编辑器中，生成的 XML 工具的实例并删除其中一个部分，例如，删除请求消息的响应部分。  
  
 如果在请求和响应部分的 278 消息上运行的验证实例命令，该消息将根据 278 架构成功验证。  
  
## <a name="an-xml-instance-generated-from-a-278-hipaa-schema-will-fail-validation"></a>从 278 HIPAA 架构生成的 XML 实例的验证将失败  
 如果你使用生成实例命令从 278 HIPAA 架构，生成的 XML 实例，然后使用该实例验证命令来验证该实例，BizTalk Server 将发布错误。  
  
## <a name="a-native-instance-generated-from-a-837-schema-incorrectly-sets-gs08"></a>错误地从 837 架构生成的本地实例设置 GS08  
 生成本地实例使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，它包含 X12_BatchSchema 以及 837I 或 837p 架构，GS08 的值将包含 00401。 在处理前此实例，必须为架构实例的正确值更改 GS08 的值。  下表包含每个 837 架构正确 GS08 值：  
  
|HIPAA 架构|GS08 值|  
|------------------|----------------|  
|837I|004010X096A1|  
|837D|004010X097A1|  
|837P|004010X098A1|  
  
## <a name="see-also"></a>请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [使用 XML 工具扩展](../core/using-the-xml-tool-extensions.md)   
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)