---
title: "管理 BizTalk Server 开发人员项目一个的源控制系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce25b112-38c9-40c8-9a5f-a2855572aabb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 829749911bd4f3ca6aee1da42578a1aac28db7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-biztalk-server-developer-artifacts-with-a-source-control-systems"></a>通过源代码管理系统管理 BizTalk Server 开发人员项目
保护 BizTalk 项目不出现意外的系统失败是重中之重。 保护项目文件的一种方法是使用源代码管理系统，如 Team Foundation Server 源代码管理和 Microsoft Visual SourceSafe。 本主题讨论了用于组织项目使之最适合与任何源代码管理系统一起使用的基本策略，之后提供了使用 Visual SourceSafe 的具体建议。  
  
## <a name="basic-organization-strategies"></a>基本组织策略  
 无论最终将使用哪种源代码管理系统，都可以遵循一些基本组织策略。 这些策略可以保证所组织的 BizTalk 项目文件结构同时适合于开发和源代码管理。  
  
### <a name="use-a-consistent-folder-structure-for-solutions-and-projects"></a>对解决方案和项目使用一致的文件夹结构  
 在团队环境中的开发更容易管理如果存储的通用结构[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]跨整个团队使用解决方案和项目。 当每个 BizTalk 项目都要生成和使用生成、测试和部署工作组所必需的某些文件（比如绑定文件）时更是如此。  
  
 开始开发时通常很容易，因为不需要花费时间对文件夹结构进行标准化。 但是，随着项目开发的进行，需要对项目链接和测试工具进行“修补”，这样势必会花费更多时间。  
  
### <a name="keep-source-control-and-file-system-structures-identical"></a>保持源代码管理和文件系统结构完全相同  
 为了简化多开发人员环境的管理，请在源代码管理系统中设置一个与本地文件系统结构相匹配的文件夹结构。 这有助于确保开发人员获得最新版本，并确定磁盘上的结构与工作组的标准相符。  
  
### <a name="define-and-use-a-common-root-folder"></a>定义和使用公共根文件夹  
 建议将所有项目代码和可传递文件保持在可随后在所有开发人员的计算机上依次创建的单一文件夹根下。 当所有开发人员都使用同一个根时，管理开发项目和保持一致配置的过程即会得以简化。 例如，在 Visual SourceSafe 中创建一个根文件夹 $/SysInteg2009 后，所有开发人员都可以在其本地文件系统上创建 C:\SysInteg2009。  
  
### <a name="create-a-master-solution-that-will-hold-all-projects"></a>创建将容纳所有项目的主解决方案  
 主解决方案通常用作主生成解决方案。 建议对中高复杂程度的 BizTalk 项目应用此策略。  
  
### <a name="store-all-biztalk-projects-under-the-master-solution"></a>将所有 BizTalk 项目存储在主解决方案下  
 将所有相关的 BizTalk 项目都组织在主解决方案下很有用。 源代码管理系统中的结构应该反映这一层次结构。  
  
### <a name="divide-the-folder-structure-into-shared-and-process-specific-sections"></a>将文件夹结构拆分为共享部分和特定于流程的部分  
 创建文件结构时，通常需要拆分文件夹结构以区别共享实体和特定于业务流程的实体。 共享实体是多个项目的公共实体，可能包括帮助器类。  
  
 例如，下面列表中的前三个文件夹按共享实体进行组织，后两个文件夹按业务流程进行组织：  
  
 C:\SysInteg2009\\_Master_Solution\Shared\  
  
 C:\SysInteg2009\\_Master_Solution\Shared\EmailHelper  
  
 C:\SysInteg2009\\_Master_Solution\Shared\SharedSchema  
  
 C:\SysInteg2009\\_Master_Solution\AccountRequest\  
  
 C:\SysInteg2009\\_Master_Solution\AccountValidate\  
  
### <a name="separate-pipeline-projects-into-distinct-projects"></a>将管道项目拆分为不同的项目  
 在管道组件的开发过程中，通常要求独立于解决方案的其余部分来修改和重新测试管道。 因此，将管道解决方案保持为独立的 BizTalk 项目很有帮助，这样可以使生成一个独立的管道程序集，无需重新绑定解决方案的其余部分即可以删除并重新部分该管道程序集。  
  
 此外，它是常见的做法，以使代码实现的实际管道接口和管道处理从 BizTalk 项目 （包含.btp 文件） 的逻辑在单独的项目的引用，到[!INCLUDE[btsCSharp](../includes/btscsharp-md.md)]或 Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]项目。  
  
### <a name="keep-deployment-and-test-scripts-with-their-projects"></a>将部署和测试脚本与其项目保持在一起  
 为了实现统一的生成和部署开发过程，生成脚本和安装脚本应当由单独的开发人员生成，这些脚本应视为完整解决方案的可重复使用部分。 如果编写的脚本可以重复使用，则像部署整个解决方案包这样的任务可以重复使用这些脚本。 例如，如果已部署和取消部署脚本接受参数来指定的 DLL 和绑定文件文件夹位置的路径，脚本可能会重复使用时已编译[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]程序集位于不同的位置。  
  
 使用此方法，开发人员可以将其特定进程的安装脚本添加到文件夹，然后，只需要编写一个简单的进程即可以执行所有进程的完全部署。  
  
### <a name="use-unique-strong-name-keys-when-appropriate"></a>适当时使用唯一的强名称密钥  
 通常一个[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案使用单个密钥文件。 这是因为解决方案被视为单个实体，并按单个实体进行管理。 如果开发的业务解决方案实际上由两个或多个不同部分组成，则应考虑是否要使用两个密钥文件。 在这种情况下，多个密钥使各个部分将被视为独立的实体（例如升级路径不同的情况）。  
  
 同样的注意事项适用于帮助器项目。 如果帮助器项目是（或将是）独立的实体，则应该使用单独的强名称密钥生成该项目。  
  
### <a name="put-dependent-dlls-into-a-separate-folder"></a>将独立的 DLL 放在单独的文件夹中  
 创建文件夹结构时，创建一个容纳作为文件依存关系而被引用的 DLL 的公共文件夹很有帮助。 通过确保所有开发人员都使用同样的文件夹结构，当在开发人员之间或工作站之间移动解决方案时，文件引用不会被破坏。  
  
### <a name="keep-test-messages-in-a-msgs-folder"></a>将测试消息保存在“Msgs”文件夹中  
 在开发架构和使用消息时，根据 XML 架构和业务流程测试众多不同示例消息时通常需要大量工作。  
  
 在实际的解决方案中，示例消息是一笔宝贵的资产，因为它们包含的数据对业务解决方案具有重要意义。 同一个消息中的随机值或虚拟值通常会导致进程失败。 因此，示例消息应当与解决方案代码同样对待。  
  
 为帮助管理消息文件，应将测试消息保存在名为“msgs”的特定文件夹下。 在同时具有“生成的实例”和“示例消息”的情况下（例如来自现有系统的消息），有必要单独保存这些消息，以便在开发的架构和实际数据之间进行比较。  
  
 集成项目中通常具有多个版本的架构，因此具有多个版本的消息文件。 为了区分示例消息，可以在命名文件时使用版本号。  
  
### <a name="managing-other-files"></a>管理其他文件  
 某些类型的文件可以分组并存储在不同的文件夹中；其余类型的文件可以与其他文件一起存储在公共文件夹中。 制定有关如何处理每种文件类型的策略，然后一贯执行。  
  
## <a name="working-with-biztalk-server-and-visual-sourcesafe"></a>使用 BizTalk Server 和 Visual SourceSafe  
 本部分讨论使用 Visual SourceSafe 时的具体注意事项，包括处理 Unicode、使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 进行源代码管理、何时检入、版本控制和其他问题。  
  
### <a name="solution-character-sets"></a>解决方案字符集  
 Visual SourceSafe 在处理 Unicode 文件方面有一条已知限制。 使用 BizTalk 解决方案时，必须防止 Visual SourceSafe 损坏 BizTalk Server Unicode 文件。  
  
##### <a name="to-enable-visual-sourcesafe-to-work-with-biztalk-server-unicode-files"></a>启用 Visual SourceSafe 以使用 BizTalk Server Unicode 文件  
  
1.  启动 Visual SourceSafe 8.0 管理员联系。  
  
2.  选择要使用的 SourceSafe 数据库。  
  
3.  在“工具”  菜单上，单击“选项” 。  
  
4.  单击**文件类型**选项卡。  
  
5.  将以下文件类型添加到二进制文件列表的末尾。 检查每个文件类型之间是否有分号：  
  
     *.btm;\*.btp;\*.xsd;\*.odx  
  
6.  单击 **“确定”**。  
  
 现在，Visual SourceSafe 不会再检查 BizTalk Server 文件并尝试更改这些文件的格式。  
  
### <a name="use-visual-studio-for-source-control-operations"></a>使用 Visual Studio 进行源代码管理操作  
 所有项目创建和操作 Visual SourceSafe 中的应执行通过使用集成的 Visual SourceSafe 支持菜单内[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 不要使用 Visual SourceSafe Explorer 执行这些操作。  
  
### <a name="when-to-check-in-biztalk-server-projects"></a>何时检入 BizTalk Server 项目  
 使用 Visual SourceSafe 时，建议仅在代码已成功通过功能测试且开发人员确信该代码会成功生成而不会中断任何其他代码时，才检入该代码。 应用到此模型[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]导致以下准则：  
  
-   仅包含消息架构的 BizTalk 项目只应在这些架构已经成功根据各种示例消息进行测试后才能检入。  
  
-   包含业务流程的 BizTalk 项目只应在使用相应的输入和输出消息并使用正确的发送和接收端口成功进行测试解决方案后才能检入。  
  
-   ASP.NET Web Services 项目只应在已经根据初始系统或使用测试工具对 Web Services 代码进行测试后才能检入。  
  
 如果遵循此模式，则 Visual SourceSafe 储存库将始终保存一个可以成功生成和测试的内部版本。 如果要按照“夜间生成”方法操作，则必须遵循此原则。  
  
### <a name="checking-in-intermediate-versions"></a>检入中间版本  
 检入文件的另一种方法是检入“中间”版本。 在这种方法中，中间版本尚未成功通过功能测试，可以认为是“内部中间版本”。 通常不推荐使用此方法，因为它违反了一般原则，即始终在源代码管理系统中拥有可生成版本。 但一些工作组喜欢使用这种方法，因为它允许开发人员使用源代码管理系统检入和回滚各个版本，而不需满足检入正式版本的条件。  
  
 如果需要使用检入中间版本这一方法，则不能认为源代码管理系统中包含“可生成”版本。 相反，您必须区分中间版本和内部版本。 这可以通过使用以下自动进行或基于进程的 Visual SourceSafe 得以实现。 例如：  
  
-   开发人员在将“可生成”版本添加到 Visual SourceSafe 时通知内部版本管理器。  
  
-   开发人员将经过测试并准备生成的版本检入到 Visual SourceSafe 的“提示区域”中。 之后，此提示区域用做主版本所依据的源。  
  
-   编写代码或脚本时可以让其使用 Visual SourceSafe COM 接口。 例如，可以使用特定标签以表明代码已准备好进行生成，脚本搜索此标签，然后将此源代码“钉”入到单独的 Visual SourceSafe 分支中。 然后，将此分支用做主内部版本的源。  
  
### <a name="comparing-files"></a>比较文件  
 您可以使用 Visual SourceSafe 来查找两个不同版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 源文件之间的区别。 此操作可以对各种项目执行，包括映射和架构及其相关文件，如消息，甚至是导出的配置文件。  
  
> [!NOTE]
>  比较映射时，您必须在签入映射之前编辑映射，否则，Visual SourceSafe 将在查找该映射与下一版本之间的区别时执行二进制比较。 这是因为编码信息在编辑后才添加到映射 XML。  
  
### <a name="version-controlling-non-biztalk-server-project-files"></a>对 BizTalk Server 项目文件进行版本控制  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 还使用一些附加文件，这些文件在 Visual SourceSafe 中进行版本控制和存储时别具优势。 以下文件为示例文件：  
  
-   绑定文件（开发和测试）  
  
-   自定义管道程序集  
  
-   测试数据（例如测试消息）  
  
-   测试工具（在项目生存期内可能发生变化）  
  
-   可能需要在部署和生成工作组之间共享的生成脚本、部署脚本和启动停止脚本  
  
 如果这些文件将与特定[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 项目，然后它们可以包含 BizTalk 项目中并由使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]集成源控制功能。  
  
##### <a name="to-include-a-file-or-folder-into-an-existing-visual-studio-project"></a>将文件或文件夹包括在现有的 Visual Studio 项目中  
  
1.  在解决方案资源管理器，单击**显示所有文件**。  
  
2.  选择要包括在解决方案中的文件夹或文件。  
  
3.  右键单击该文件夹或文件，并依次**包括在项目**。  
  
> [!NOTE]
>  Visual SourceSafe 资源管理器不应该用于管理属于的任何项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目受源代码管理。  
  
### <a name="checking-the-visual-sourcesafe-database"></a>检查 Visual SourceSafe 数据库  
 如果 Visual SourceSafe 数据库很大且使用频繁，或由许多并发用户进行访问，则建议定期从 Visual SourceSafe 菜单中运行“Analyze VSS DB”命令。 如果分析过程中检测到错误，可以通过使用“Analyze and Fix VSS DB”命令修复这些错误。 这两个命令都需要锁定 Visual SourceSafe 数据库，因此要求每个人都与 Visual SourceSafe 断开连接。