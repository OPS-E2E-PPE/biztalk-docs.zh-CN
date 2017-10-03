---
title: "将博士 Edwards OneWorld 架构导入到 BizTalk Server 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b0d7fec5acc991ae6c141f57297b7511281be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a>将 JD Edwards OneWorld 架构导入到 BizTalk Server 项目中
本主题讨论如何浏览 JD Edwards OneWorld 服务器，并将架构导入到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中。  
  
> [!NOTE]
>  您必须确保已设置 arglist。 在业务流程中生成架构之前，您必须先更新 jdearglist.txt。 有关详细信息，请参阅[处理字符串值](../core/handling-string-values1.md)。  
  
> [!NOTE]
>  每次更改 jdearglist 时，都必须为该业务对象重新生成架构。  
  
 在创建 JD Edwards OneWorld 逻辑系统之后，您可以通过打开 BizTalk Server 项目中的 Microsoft 适配器向导来浏览 JD Edwards OneWorld。  
  
### <a name="to-import-schemas"></a>若要导入架构  
  
1.  打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2.  右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。  
  
3.  单击**添加适配器**，然后选择**打开**。  
  
4.  选择适配器，然后单击**下一步**。  
  
     博士。 Edwards OneWorld XE 系统将显示在浏览器中。  
  
     ![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")  
  
     适配器向导会显示所有已定义的系统树。 JD Edwards OneWorld 的模块太多，无法显示在一个较长的列表中。 这些模块根据其名称的前三个字符组合在一起。  
  
    -   层次结构的第一层是该模块名称所有三个字符前缀的列表。  
  
    -   第二层列出所有共享相同三字符前缀的模块。  
  
    -   最后一层列出属于某个模块的业务功能。 当您展开服务图标时，可以查看其操作。  
  
     展开某项操作后，将显示输入/输出参数。  
  
     您可以展开输入/输出参数以查看该参数的数据类型。  
  
    > [!NOTE]
    >  如果服务器对象定义发生更改，您必须重新生成架构以刷新其包含的数据。  
  
    > [!NOTE]
    >  如果您在生成架构后更改了 jdearglist.txt，则必须重新生成架构以刷新其包含的数据。 有关 jdearglist.txt 的信息，请参阅[处理字符串值](../core/handling-string-values1.md)。  
  
## <a name="generating-schemas"></a>生成架构  
 使用以下过程来生成架构。  
  
#### <a name="to-generate-schemas"></a>若要生成架构  
  
1.  选择要导入架构的项目。  
  
2.  单击 （或拖动） 若要向其中添加项**传输**窗格中 （对于一个到 J.Edwards OneWorld 的入站调用）。  
  
3.  单击 **“确定”**。  
  
     将为选定 JD Edwards OneWorld 项目生成的构架导入到 BizTalk Server 项目。  
  
> [!NOTE]
>  在使用通讯簿 (N0100041) 的字段名称是**cActionCode**。 此操作是 XML 文件自身的一部分。 这些代码为：  
>   
>  -A 的添加  
>   
>  --C 表示更改  
>   
>  -D 删除  
>   
>  --I 表示查询  
  
## <a name="see-also"></a>另请参阅  
 [创建博士 Edwards OneWorld 发送处理程序](../core/creating-jd-edwards-oneworld-send-handlers.md)