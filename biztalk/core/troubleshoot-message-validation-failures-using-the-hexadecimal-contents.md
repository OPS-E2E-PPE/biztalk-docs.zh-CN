---
title: 通过查看挂起的消息的十六进制内容来解决消息验证失败 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279565"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a>通过查看挂起的消息的十六进制内容来解决消息验证失败
如果消息由于验证失败而挂起，通过查看消息部分的十六进制表示形式可以帮助确定导致验证失败的原因。 本主题列出了查看挂起消息部分的十六进制表示形式时应遵循的步骤。  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a>使用“消息详细信息”对话框查看消息部分  
 请遵循以下这些步骤查看消息部分的十六进制表示形式：  
  
1.  使用**查询**在 BizTalk 管理控制台中返回的结果集与一个或多个挂起的消息的选项卡。 请参阅[如何搜索消息](../core/how-to-search-for-messages.md)有关详细信息。  
  
2.  双击你想要进行调查以显示该挂起的消息**消息详细信息**消息的对话框。  
  
3.  单击左侧窗格中的消息部分**消息详细信息**对话框以显示消息部分。  
  
    > [!NOTE]
    >  消息可能没有或者有一个或多个消息部分。 大部分消息通常只有一个消息部分，称作“正文”。  
  
4.  单击**二进制**的右窗格中的选项卡**消息详细信息**对话框中显示的十六进制表示形式的消息部分。  
  
5.  检查消息部分中字符的十六进制表示形式的以下各项：  
  
    -   缺少字节顺序标记或字节顺序标记无效。 有关字节顺序标记请参阅[http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)。  
  
    -   Unix 和 Windows 中的换行符编码不同。 Unix 使用十六进制换行符 (0A) 指示换行，而 Windows 使用十六进制回车符 (0D) 和换行符 (0A) 一起指示换行。  
  
    -   消息部分中有无效控制字符。 消息部分中在文本视图下不显示的控制字符在二进制视图中可能可见。  
  
    -   消息部分中的无效空字符会导致消息部分截断。 空字符表示为十六进制值 (00)。  
  
    -   位置平面文件中的无效字符偏移量。 显示消息部分的十六进制表示形式，以查看位置平面文件中的数据偏移量。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)