---
title: 用于 EDI 解决方案的 XML 工具的已知问题 |Microsoft 文档
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
ms.openlocfilehash: 23b8222369503f616f2d994f9292091f8e6c1f0d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008718"
---
# <a name="known-issues-with-xml-tools-used-with-edi-solutions"></a>XML 工具与 EDI 解决方案一起使用时的已知问题
本主题介绍与 BizTalk Server 中的 XML 工具的已知的问题。  
  
## <a name="validation-of-test-map-input-and-output-file-still-occurs-when-the-validate-property-is-set-to-false"></a>当验证属性设置为“False”时仍对测试映射输入和输出文件进行验证  
 如果测试映射测试映射输入属性设置为**本机**和验证测试映射输入和验证测试映射输出属性设置为**False**，仍将执行验证。 这是因为本机格式输入文件将被转换为 XML 格式，并且 BizTalk Server 将根据架构验证 XML。 如果输入文件不存在验证问题，此验证机制将发布错误，即使的验证测试映射输入和验证测试映射输出属性设置为**False**。  
  
## <a name="length-validation-is-not-performed-on-a-data-element-in-a-generated-instance-that-is-pulled-from-an-enum-list-in-the-schema"></a>不对生成的实例中从架构的枚举列表中提取的数据元素执行长度验证。  
 当从某一架构生成一个实例，且该架构中的数据元素的枚举值不符合长度要求时，则生成的实例中可能会存在因不满足长度要求而导致 XSD 验证失败的数据元素。 架构验证将不检查生成的实例中从架构的枚举列表中提取的值是否符合最小/最大长度要求。  
  
## <a name="validate-schema-may-not-detect-an-invalid-transaction-set-id-code"></a>验证架构可能检测不到无效的事务集 ID 代码  
 当验证具有的解决方案资源管理器窗口中的验证架构命令的架构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，根节点的检查可能不检测无效的事务在根引用节点的最后部分中设置 ID 代码 (格式 X12_\<VersionRelease\>_TSID)。 如果架构的根引用节点中的 TSID 是无效的，但与架构中 ST01 元素的枚举节点中的 TSID 相同，则验证架构操作将检测不出该 TSID 是无效的。  
  
## <a name="visual-studio-must-be-restarted-to-make-an-enum-change-in-a-schema-effective-for-instance-validation"></a>必须重新启动 Visual Studio 才能使架构中的枚举更改对实例验证生效  
 如果您更改了架构中的枚举列表，保存该架构然后运行实例验证，BizTalk Server 将基于架构的上一版本而不是最新版本执行验证。 BizTalk Server 在您重新启动 Visual Studio 后才会使用架构的最新版本。  
  
## <a name="the-edi-instance-properties-dialog-box-may-be-displayed-when-not-needed-in-the-testmap-operation"></a>测试映射操作中显示不需要的“EDI 实例属性”对话框  
 BizTalk Server 将显示 EDI 实例属性对话框中，在测试映射过程两次： 一次，以便你可以输入所需的解释输入的消息实例，一次针对输入分隔符生成输出消息的分隔符实例。 BizTalk Server 应仅对 EDI 架构显示两次“EDI 实例属性”对话框，BizTalk Server 可能多次显示该对话框，并且可能针对非 EDI 架构显示该对话框。 如果出现此情况，请关闭该对话框。  
  
## <a name="validation-of-an-xml-preserved-interchange-is-not-supported"></a>不支持验证 XML 保留交换  
 在验证保留的交换，如果你选择的 XML 时**验证实例输入类型**属性，该操作将失败，并且将返回任何内容。 但是，如果你选择**本机**为**验证实例输入类型**时验证保留的交换，操作将成功。  
  
## <a name="an-instance-generated-for-a-hipaa-278-schema-will-contain-both-request-and-response-sections"></a>为 HIPAA 278 架构生成的实例将同时包含请求和响应部分  
 HIPAA 278 架构既用于 278 请求消息又用于 278 响应消息。 如果您在 278 架构上使用“生成实例”命令，则生成的实例将同时包含请求和响应部分，此实例将始终不会发送。 若要创建可使用的 278 请求或 278 响应消息，请在文本编辑器中打开 XML 工具生成的实例，然后删除其中一个部分，例如，删除请求消息的响应部分。  
  
 如果您在某一同时具有请求和响应部分的 278 消息上运行“验证实例”命令，则根据 278 架构验证该消息时将成功。  
  
## <a name="an-xml-instance-generated-from-a-278-hipaa-schema-will-fail-validation"></a>验证从 278 HIPAA 架构生成的 XML 实例失败  
 如果您使用“实例生成”命令从 278 HIPAA 架构生成 XML 实例，然后使用“实例验证”命令来验证该实例，则 BizTalk Server 将报告错误。  
  
## <a name="a-native-instance-generated-from-a-837-schema-incorrectly-sets-gs08"></a>从 837 架构生成的本地实例会错误地设置 GS08  
 生成本机实例使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含 X12_BatchSchema 以及 837I、 837 D 或 837 P 架构，GS08 的值的解决方案将包含 00401。 然后再处理此实例，必须为架构实例正确的值更改 GS08 的值。  下表包含每个 837 架构正确 GS08 值：  
  
|HIPAA 架构|GS08 值|  
|------------------|----------------|  
|837I|004010X096A1|  
|837D|004010X097A1|  
|837P|004010X098A1|  
  
## <a name="see-also"></a>另请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [使用 XML 工具扩展](../core/using-the-xml-tool-extensions.md)   
 [通过使用设计时 XML 工具](../core/using-design-time-xml-tools.md)