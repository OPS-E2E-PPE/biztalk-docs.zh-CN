---
title: JD Edwards OneWorld 架构导入到 BizTalk Server 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1950409b71ddc7773dc6ad1ddbee3591dc1d63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382456"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a>JD Edwards OneWorld 架构导入到 BizTalk Server 项目
本主题讨论浏览 JD Edwards OneWorld 服务器和导入到架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。  
  
> [!NOTE]
>  您必须确保已设置 arglist。 在业务流程中生成架构之前，必须更新 jdearglist.txt。 有关详细信息，请参阅[处理字符串值](../core/handling-string-values1.md)。  
  
> [!NOTE]
>  每次更改 jdearglist，您必须重新生成该业务对象的架构。  
  
 创建 JD Edwards OneWorld 逻辑系统之后, 可以通过打开 BizTalk Server 项目中的 Microsoft 适配器向导浏览 JD Edwards OneWorld。  
  
### <a name="to-import-schemas"></a>若要导入架构  
  
1. 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
2. 右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。  
  
3. 单击**添加适配器**，然后选择**打开**。  
  
4. 选择适配器，然后单击**下一步**。  
  
    JD。 Edwards OneWorld XE 系统将显示在浏览器。  
  
    ![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")  
  
    适配器向导会显示所有已定义的系统的树。 JD Edwards OneWorld 中有太多的模块，以显示一个长列表中。 根据其名称的前三个字符，将模块组合在一起。  
  
   - 在层次结构的第一个级别是该模块名称所有三个字符前缀的列表。  
  
   - 第二层列出所有共享相同三字符前缀的模块。  
  
   - 最后一层列出属于某个模块的业务功能。 当您展开服务图标时可以查看其操作。  
  
     展开某项操作显示的输入/输出参数。  
  
     您可以展开要查看的自变量的数据类型的输入/输出参数。  
  
   > [!NOTE]
   >  如果服务器对象定义发生更改，必须重新生成架构以刷新其包含的数据。  
  
   > [!NOTE]
   >  如果生成架构后更改了 jdearglist.txt，必须重新生成架构以刷新其包含的数据。 有关 jdearglist.txt 的信息，请参阅[处理字符串值](../core/handling-string-values1.md)。  
  
## <a name="generating-schemas"></a>生成架构  
 使用以下过程来生成架构。  
  
#### <a name="to-generate-schemas"></a>若要生成架构  
  
1.  选择你想要将架构导入的项。  
  
2.  单击 （或拖动） 以将项添加到**传输**窗格 （对于到 J.Edwards OneWorld 的入站调用）。  
  
3.  单击“确定” 。  
  
     对所选的 JD Edwards OneWorld 项目生成的架构导入 BizTalk Server 项目中。  
  
> [!NOTE]
>  使用 AddressBook (N0100041) 时的字段名称是**cActionCode**。 操作为 XML 文件本身的一部分。 这些代码为：  
>   
>  -A 代表添加  
>   
>  --C 表示更改  
>   
>  -D 代表删除  
>   
>  --I 表示查询  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)