---
title: extern 别名 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 0fd917d1af38ba558634dfcf5e3a1abf95420a9d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235367"
---
# <a name="extern-alias-c-reference"></a>外部别名（C# 参考）
有时你可能不得不引用具有相同的完全限定类型名称的程序集的两个版本。 例如，可能需要在同一应用程序中使用某程序集的两个或多个版本。 通过使用外部程序集别名，可在别名命名的根级别命名空间内包装每个程序集的命名空间，使其能够在同一文件中使用。  
  
> [!NOTE]
>  [外部](../../../csharp/language-reference/keywords/extern.md)关键字还被用作方法修饰符，用于声明在非托管代码中编写的方法。  
  
 若要引用具有相同的完全限定类型名称的两个程序集，必须在命令提示符处指定别名，如下所示：  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 这将创建外部别名 `GridV1` 和 `GridV2`。 若要从程序中使用这些别名，请通过使用 `extern` 关键字引用它们。 例如:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 每个外部别名声明都会引入与全局命名空间并行（但不位于其中）的额外根级别命名空间。 因此，可以使用其完全限定的名称（根植于相应的命名空间别名中）无歧义地引用每个程序集的类型。  
  
 在上一示例中，`GridV1::Grid` 是 `grid.dll` 中的网格控件，`GridV2::Grid` 是 `grid20.dll` 中的网格控件。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
- [命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [::运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [/reference（C# 编译器选项）](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
