---
title: 正则表达式 2 语法
ms.author: comanea
author: dan-wesley
manager: seanlyn
ms.date: 06/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: 正则表达式 2 语法
ms.openlocfilehash: 5d7026a034300e098497c63911f7516f72877c5d
ms.sourcegitcommit: 4192328ee585bc32a9be528766b8a5a98e046c8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "11617312"
---
# <a name="regular-expression-2-re2h-syntax"></a><span data-ttu-id="1de74-103">正则表达式 2 (re2.h) 语法</span><span class="sxs-lookup"><span data-stu-id="1de74-103">Regular Expression 2 (re2.h) syntax</span></span>

<span data-ttu-id="1de74-104">正则表达式是描述字符串集的表示法。</span><span class="sxs-lookup"><span data-stu-id="1de74-104">Regular expressions are a notation for describing sets of character strings.</span></span> <span data-ttu-id="1de74-105">如果字符串位于正则表达式所描述的集合中，通常表示正则表达式匹配该字符串。</span><span class="sxs-lookup"><span data-stu-id="1de74-105">When a string is in the set described by a regular expression, we often say that the regular expression matches the string.</span></span>

<span data-ttu-id="1de74-106">最简单的正则表达式是单个文本字符。</span><span class="sxs-lookup"><span data-stu-id="1de74-106">The simplest regular expression is a single literal character.</span></span> <span data-ttu-id="1de74-107">除了 *\*+?()|* 等元字符，字符匹配自身。</span><span class="sxs-lookup"><span data-stu-id="1de74-107">Except for the metacharacters like *\*+?()|*, characters match themselves.</span></span> <span data-ttu-id="1de74-108">若要匹配元字符，请使用反斜杠将其转义，如： \+ 匹配加号字符。</span><span class="sxs-lookup"><span data-stu-id="1de74-108">To match a metacharacter, escape it with a backslash: \+ matches a literal plus character.</span></span>

<span data-ttu-id="1de74-109">可以更改或连接两个正则表达式，形成一个新的正则表达式：如果 *e<sub>1</sub>* 匹配 _s_，*e<sub>2</sub>* 匹配 _t_，则 *e<sub>1</sub> \* | *e<sub>2</sub>* 匹配 _s_ 或 _t_，而且*e<sub>1</sub>\* *e<sub>2</sub>* 匹配 _st_。</span><span class="sxs-lookup"><span data-stu-id="1de74-109">Two regular expressions can be altered or concatenated to form a new regular expression: if *e<sub>1</sub>* matches _s_ and *e<sub>2</sub>* matches _t_, then *e<sub>1</sub>* | *e<sub>2</sub>* matches _s_ or _t_, and *e<sub>1</sub>* *e<sub>2</sub>*  matches _st_.</span></span>

<span data-ttu-id="1de74-110">元字符 _\*_、_+_ 和 _?_</span><span class="sxs-lookup"><span data-stu-id="1de74-110">The metacharacters _\*_ , _+_ , and _?_</span></span> <span data-ttu-id="1de74-111">是重复运算符： *e<sub>1</sub>* _\*_ 匹配零个或多个（可能是不同的）字符串序列，其中每个字符串匹配 *e<sub>1</sub>*；*e<sub>1</sub>* _+_ 匹配一个或多个；*e<sub>1</sub>* _?_</span><span class="sxs-lookup"><span data-stu-id="1de74-111">are repetition operators: *e<sub>1</sub>* _\*_ matches a sequence of zero or more (possibly different) strings, each of which match *e<sub>1</sub>*; *e<sub>1</sub>* _+_ matches one or more; *e<sub>1</sub>* _?_</span></span> <span data-ttu-id="1de74-112">匹配零个或一个。</span><span class="sxs-lookup"><span data-stu-id="1de74-112">matches zero or one.</span></span>

<span data-ttu-id="1de74-113">运算符的优先级从最弱到最强排序，依次是替换、连接和重复运算符。</span><span class="sxs-lookup"><span data-stu-id="1de74-113">The operator precedence, from weakest to strongest binding, is first alternation, then concatenation, and finally the repetition operators.</span></span> <span data-ttu-id="1de74-114">可采用显式括号强制改变运算顺序，就像在算术表达式中一样。</span><span class="sxs-lookup"><span data-stu-id="1de74-114">Explicit parentheses can be used to force different meanings, just as in arithmetic expressions.</span></span> <span data-ttu-id="1de74-115">示例： _ab|cd_ 等同于 _(ab)|(cd)_；_ab\*_ 等同于 _a(b\*)_ 。</span><span class="sxs-lookup"><span data-stu-id="1de74-115">Some examples: _ab|cd_ is equivalent to _(ab)|(cd)_ ; _ab\*_ is equivalent to _a(b\*)_ .</span></span>

<span data-ttu-id="1de74-116">目前所介绍的语法大部分为传统的 Unix _egrep_ 正则表达式语法。</span><span class="sxs-lookup"><span data-stu-id="1de74-116">The syntax described so far is most of the traditional Unix _egrep_ regular expression syntax.</span></span> <span data-ttu-id="1de74-117">此子集足以描述所有常规语言：笼统来讲，常规语言是一组字符串，可在单个传递文本的过程中仅使用固定数量的内存进行匹配。</span><span class="sxs-lookup"><span data-stu-id="1de74-117">This subset suffices to describe all regular languages: loosely speaking, a regular language is a set of strings that can be matched in a single pass through the text using only a fixed amount of memory.</span></span> <span data-ttu-id="1de74-118">较新的正则表达式功能（尤其是 Perl 和那些已复制的功能）添加了许多新的运算符和转义序列，令正则表达式更简洁，有时含义模糊，但通常功能没有增强。</span><span class="sxs-lookup"><span data-stu-id="1de74-118">Newer regular expression facilities (notably Perl and those that have copied it) have added many new operators and escape sequences, which make the regular expressions more concise, and sometimes more cryptic, but usually not more powerful.</span></span>

<span data-ttu-id="1de74-119">本页列出了 RE2 接受的正则表达式语法。</span><span class="sxs-lookup"><span data-stu-id="1de74-119">This page lists the regular expression syntax accepted by RE2.</span></span>

<span data-ttu-id="1de74-120">还列出了 PCRE、PERL 和 VIM 接受的一些语法。</span><span class="sxs-lookup"><span data-stu-id="1de74-120">It also lists some syntax accepted by PCRE, PERL and VIM.</span></span>

## <a name="syntax-tables"></a><span data-ttu-id="1de74-121">语法表</span><span class="sxs-lookup"><span data-stu-id="1de74-121">Syntax tables</span></span>

| <span data-ttu-id="1de74-122">单字符表达式的类型</span><span class="sxs-lookup"><span data-stu-id="1de74-122">Kinds of single-character expressions</span></span> | <span data-ttu-id="1de74-123">示例</span><span class="sxs-lookup"><span data-stu-id="1de74-123">Examples</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-124">任何字符，可能包括换行符（s = true）</span><span class="sxs-lookup"><span data-stu-id="1de74-124">any character, possibly including newline (s=true)</span></span> | <span data-ttu-id="1de74-125">.</span><span class="sxs-lookup"><span data-stu-id="1de74-125">.</span></span> |
| <span data-ttu-id="1de74-126">字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-126">character class</span></span> | <span data-ttu-id="1de74-127">[xyz]</span><span class="sxs-lookup"><span data-stu-id="1de74-127">[xyz]</span></span> |
| <span data-ttu-id="1de74-128">排除型字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-128">negated character class</span></span> | <span data-ttu-id="1de74-129">[^xyz]</span><span class="sxs-lookup"><span data-stu-id="1de74-129">[^xyz]</span></span> |
| <span data-ttu-id="1de74-130">Perl 字符组（[链接](#user-content-perl)）</span><span class="sxs-lookup"><span data-stu-id="1de74-130">Perl character class ([link](#user-content-perl))</span></span> | <span data-ttu-id="1de74-131">\d</span><span class="sxs-lookup"><span data-stu-id="1de74-131">\d</span></span> |
| <span data-ttu-id="1de74-132">排除型 Perl 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-132">negated Perl character class</span></span> | <span data-ttu-id="1de74-133">\D</span><span class="sxs-lookup"><span data-stu-id="1de74-133">\D</span></span> |
| <span data-ttu-id="1de74-134">ASCII 字符组（[链接](#user-content-ascii)）</span><span class="sxs-lookup"><span data-stu-id="1de74-134">ASCII character class ([link](#user-content-ascii))</span></span> | <span data-ttu-id="1de74-135">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-135">[[:alpha:]]</span></span> |
| <span data-ttu-id="1de74-136">排除型 ASCII 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-136">negated ASCII character class</span></span> | <span data-ttu-id="1de74-137">[[:^alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-137">[[:^alpha:]]</span></span> |
| <span data-ttu-id="1de74-138">Unicode 字符组（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="1de74-138">Unicode character class (one-letter name)</span></span> | <span data-ttu-id="1de74-139">\pN</span><span class="sxs-lookup"><span data-stu-id="1de74-139">\pN</span></span> |
| <span data-ttu-id="1de74-140">Unicode 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-140">Unicode character class</span></span> | <span data-ttu-id="1de74-141">\p{Greek}</span><span class="sxs-lookup"><span data-stu-id="1de74-141">\p{Greek}</span></span> |
| <span data-ttu-id="1de74-142">排除型 Unicode 字符组（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="1de74-142">negated Unicode character class (one-letter name)</span></span> | <span data-ttu-id="1de74-143">\PN</span><span class="sxs-lookup"><span data-stu-id="1de74-143">\PN</span></span> |
| <span data-ttu-id="1de74-144">排除型 Unicode 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-144">negated Unicode character class</span></span> | <span data-ttu-id="1de74-145">\P{Greek}</span><span class="sxs-lookup"><span data-stu-id="1de74-145">\P{Greek}</span></span> |

|&nbsp;| <span data-ttu-id="1de74-146">复合匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-146">Composites</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-147">xy</span><span class="sxs-lookup"><span data-stu-id="1de74-147">xy</span></span> | <span data-ttu-id="1de74-148">匹配 x 后接 y</span><span class="sxs-lookup"><span data-stu-id="1de74-148">x followed by y</span></span> |
| <span data-ttu-id="1de74-149">x\|y</span><span class="sxs-lookup"><span data-stu-id="1de74-149">x\|y</span></span> | <span data-ttu-id="1de74-150">匹配 x 或 y （首选 x）</span><span class="sxs-lookup"><span data-stu-id="1de74-150">x or y (prefer x)</span></span> |

|&nbsp;| <span data-ttu-id="1de74-151">重复匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-151">Repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-152">x\*</span><span class="sxs-lookup"><span data-stu-id="1de74-152">x\*</span></span> | <span data-ttu-id="1de74-153">匹配零个或任意个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-153">zero or more x, prefer more</span></span> |
| <span data-ttu-id="1de74-154">x+</span><span class="sxs-lookup"><span data-stu-id="1de74-154">x+</span></span> | <span data-ttu-id="1de74-155">匹配至少一个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-155">one or more x, prefer more</span></span> |
| <span data-ttu-id="1de74-156">x?</span><span class="sxs-lookup"><span data-stu-id="1de74-156">x?</span></span> | <span data-ttu-id="1de74-157">匹配零个或一个 x，首选一个</span><span class="sxs-lookup"><span data-stu-id="1de74-157">zero or one x, prefer one</span></span> |
| <span data-ttu-id="1de74-158">x{n,m}</span><span class="sxs-lookup"><span data-stu-id="1de74-158">x{n,m}</span></span> | <span data-ttu-id="1de74-159">匹配 n 或 n+1...至多 m 个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-159">n or n+1 or ... or m x, prefer more</span></span> |
| <span data-ttu-id="1de74-160">x{n,}</span><span class="sxs-lookup"><span data-stu-id="1de74-160">x{n,}</span></span> | <span data-ttu-id="1de74-161">匹配至少 n 个 x，首选多匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-161">n or more x, prefer more</span></span> |
| <span data-ttu-id="1de74-162">x{n}</span><span class="sxs-lookup"><span data-stu-id="1de74-162">x{n}</span></span> | <span data-ttu-id="1de74-163">匹配确定的 n 个 x</span><span class="sxs-lookup"><span data-stu-id="1de74-163">exactly n x</span></span> |
| <span data-ttu-id="1de74-164">x\*?</span><span class="sxs-lookup"><span data-stu-id="1de74-164">x\*?</span></span> | <span data-ttu-id="1de74-165">匹配零个或任意个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-165">zero or more x, prefer fewer</span></span> |
| <span data-ttu-id="1de74-166">x+?</span><span class="sxs-lookup"><span data-stu-id="1de74-166">x+?</span></span> | <span data-ttu-id="1de74-167">匹配至少一个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-167">one or more x, prefer fewer</span></span> |
| <span data-ttu-id="1de74-168">x??</span><span class="sxs-lookup"><span data-stu-id="1de74-168">x??</span></span> | <span data-ttu-id="1de74-169">匹配零个或一个 x，首选零个</span><span class="sxs-lookup"><span data-stu-id="1de74-169">zero or one x, prefer zero</span></span> |
| <span data-ttu-id="1de74-170">x{n,m}?</span><span class="sxs-lookup"><span data-stu-id="1de74-170">x{n,m}?</span></span> | <span data-ttu-id="1de74-171">匹配 n 或 n+1...至多m 个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-171">n or n+1 or ... or m x, prefer fewer</span></span> |
| <span data-ttu-id="1de74-172">x{n,}?</span><span class="sxs-lookup"><span data-stu-id="1de74-172">x{n,}?</span></span> | <span data-ttu-id="1de74-173">匹配至少 n 个 x，首选少匹配</span><span class="sxs-lookup"><span data-stu-id="1de74-173">n or more x, prefer fewer</span></span> |
| <span data-ttu-id="1de74-174">x{n}?</span><span class="sxs-lookup"><span data-stu-id="1de74-174">x{n}?</span></span> | <span data-ttu-id="1de74-175">匹配确定的 n 个 x</span><span class="sxs-lookup"><span data-stu-id="1de74-175">exactly n x</span></span> |
| <span data-ttu-id="1de74-176">x{}</span><span class="sxs-lookup"><span data-stu-id="1de74-176">x{}</span></span> | <span data-ttu-id="1de74-177">（等价于 x\*）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-177">(≡ x\*) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-178">x{-}</span><span class="sxs-lookup"><span data-stu-id="1de74-178">x{-}</span></span> | <span data-ttu-id="1de74-179">（等价于 x\*?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-179">(≡ x\*?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-180">x{-n}</span><span class="sxs-lookup"><span data-stu-id="1de74-180">x{-n}</span></span> | <span data-ttu-id="1de74-181">（等价于 x{n}?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-181">(≡ x{n}?) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-182">x=</span><span class="sxs-lookup"><span data-stu-id="1de74-182">x=</span></span> | <span data-ttu-id="1de74-183">（等价于 x?）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-183">(≡ x?) (NOT SUPPORTED) VIM</span></span> |

<span data-ttu-id="1de74-184">启动限制：计数形式 x{n,m}、x{n,} 和 x{n} 最小或最大重复个数不能超过 1000。</span><span class="sxs-lookup"><span data-stu-id="1de74-184">Implementation restriction: The counting forms x{n,m}, x{n,}, and x{n} reject forms that create a minimum or maximum repetition count above 1000.</span></span> <span data-ttu-id="1de74-185">无限制的重复不受此限制约束。</span><span class="sxs-lookup"><span data-stu-id="1de74-185">Unlimited repetitions are not subject to this restriction.</span></span>

|&nbsp;| <span data-ttu-id="1de74-186">所有格重复</span><span class="sxs-lookup"><span data-stu-id="1de74-186">Possessive repetitions</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-187">x\*+</span><span class="sxs-lookup"><span data-stu-id="1de74-187">x\*+</span></span> | <span data-ttu-id="1de74-188">匹配零个或任意个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-188">zero or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-189">x++</span><span class="sxs-lookup"><span data-stu-id="1de74-189">x++</span></span> | <span data-ttu-id="1de74-190">匹配至少一个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-190">one or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-191">x?+</span><span class="sxs-lookup"><span data-stu-id="1de74-191">x?+</span></span> | <span data-ttu-id="1de74-192">匹配零个或一个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-192">zero or one x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-193">x {n，m} +</span><span class="sxs-lookup"><span data-stu-id="1de74-193">x{n,m}+</span></span> | <span data-ttu-id="1de74-194">匹配 n...或 m 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-194">n or ... or m x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-195">x{n,}+</span><span class="sxs-lookup"><span data-stu-id="1de74-195">x{n,}+</span></span> | <span data-ttu-id="1de74-196">匹配至少 n 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-196">n or more x, possessive (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-197">x{n}+</span><span class="sxs-lookup"><span data-stu-id="1de74-197">x{n}+</span></span> | <span data-ttu-id="1de74-198">匹配确定的 n 个 x，所有格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-198">exactly n x, possessive (NOT SUPPORTED)</span></span> |

|&nbsp;| <span data-ttu-id="1de74-199">分组</span><span class="sxs-lookup"><span data-stu-id="1de74-199">Grouping</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-200">(re)</span><span class="sxs-lookup"><span data-stu-id="1de74-200">(re)</span></span> | <span data-ttu-id="1de74-201">编号捕获组（子匹配）</span><span class="sxs-lookup"><span data-stu-id="1de74-201">numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="1de74-202">(?P&lt;name&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1de74-202">(?P&lt;name&gt;re)</span></span> | <span data-ttu-id="1de74-203">命名 &amp; 编号捕获组（子匹配）</span><span class="sxs-lookup"><span data-stu-id="1de74-203">named &amp; numbered capturing group (submatch)</span></span> |
| <span data-ttu-id="1de74-204">(?&lt;name&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1de74-204">(?&lt;name&gt;re)</span></span> | <span data-ttu-id="1de74-205">命名 &amp; 编号捕获组（子匹配）（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-205">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-206">(?&#39;name&#39;re)</span><span class="sxs-lookup"><span data-stu-id="1de74-206">(?&#39;name&#39;re)</span></span> | <span data-ttu-id="1de74-207">命名 &amp; 编号捕获组（子匹配）（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-207">named &amp; numbered capturing group (submatch) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-208">(?:re)</span><span class="sxs-lookup"><span data-stu-id="1de74-208">(?:re)</span></span> | <span data-ttu-id="1de74-209">非捕获组</span><span class="sxs-lookup"><span data-stu-id="1de74-209">non-capturing group</span></span> |
| <span data-ttu-id="1de74-210">(?flags)</span><span class="sxs-lookup"><span data-stu-id="1de74-210">(?flags)</span></span> | <span data-ttu-id="1de74-211">在当前组中设置标志；非捕获</span><span class="sxs-lookup"><span data-stu-id="1de74-211">set flags within current group; non-capturing</span></span> |
| <span data-ttu-id="1de74-212">(?flags:re)</span><span class="sxs-lookup"><span data-stu-id="1de74-212">(?flags:re)</span></span> | <span data-ttu-id="1de74-213">在表达式中设置标志；非捕获</span><span class="sxs-lookup"><span data-stu-id="1de74-213">set flags during re; non-capturing</span></span> |
| <span data-ttu-id="1de74-214">(?#text)</span><span class="sxs-lookup"><span data-stu-id="1de74-214">(?#text)</span></span> | <span data-ttu-id="1de74-215">注释（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-215">comment (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-216">(?\|x\|y\|z)</span><span class="sxs-lookup"><span data-stu-id="1de74-216">(?\|x\|y\|z)</span></span> | <span data-ttu-id="1de74-217">分支编号重置（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-217">branch numbering reset (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-218">(?&gt;re)</span><span class="sxs-lookup"><span data-stu-id="1de74-218">(?&gt;re)</span></span> | <span data-ttu-id="1de74-219">表达式所有格匹配 （不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-219">possessive match of re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-220">re@&gt;</span><span class="sxs-lookup"><span data-stu-id="1de74-220">re@&gt;</span></span> | <span data-ttu-id="1de74-221">表达式所有格匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-221">possessive match of re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-222">%(re)</span><span class="sxs-lookup"><span data-stu-id="1de74-222">%(re)</span></span> | <span data-ttu-id="1de74-223">非捕获组（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-223">non-capturing group (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="1de74-224">Flags</span><span class="sxs-lookup"><span data-stu-id="1de74-224">Flags</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-225">i</span><span class="sxs-lookup"><span data-stu-id="1de74-225">i</span></span> | <span data-ttu-id="1de74-226">不区分大小写（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="1de74-226">case-insensitive (default false)</span></span> |
| <span data-ttu-id="1de74-227">m</span><span class="sxs-lookup"><span data-stu-id="1de74-227">m</span></span> | <span data-ttu-id="1de74-228">多行模式： ^ 和 $ 匹配行首/尾，以及文本开头/结尾（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="1de74-228">multi-line mode: ^ and $ match begin/end line in addition to begin/end text (default false)</span></span> |
| <span data-ttu-id="1de74-229">s</span><span class="sxs-lookup"><span data-stu-id="1de74-229">s</span></span> | <span data-ttu-id="1de74-230">let .</span><span class="sxs-lookup"><span data-stu-id="1de74-230">let .</span></span> <span data-ttu-id="1de74-231">匹配 \n （默认为 false）</span><span class="sxs-lookup"><span data-stu-id="1de74-231">match \n (default false)</span></span> |
| <span data-ttu-id="1de74-232">U</span><span class="sxs-lookup"><span data-stu-id="1de74-232">U</span></span> | <span data-ttu-id="1de74-233">非贪婪模式：以 x\*? 替换 x\*、x+? 替换 x+ 等（默认为 false）</span><span class="sxs-lookup"><span data-stu-id="1de74-233">ungreedy: swap meaning of x\* and x\*?, x+ and x+?, etc (default false)</span></span> |

<span data-ttu-id="1de74-234">标记语法为 xyz （已设置）或 -xyz （清除）或 xy-z （设置为 xy，清除 z）。</span><span class="sxs-lookup"><span data-stu-id="1de74-234">Flag syntax is xyz (set) or -xyz (clear) or xy-z (set xy, clear z).</span></span>

|&nbsp;| <span data-ttu-id="1de74-235">空字符串</span><span class="sxs-lookup"><span data-stu-id="1de74-235">Empty strings</span></span> |
| --- | --- |
| ^ | <span data-ttu-id="1de74-236">文本开始或行首（m = true）</span><span class="sxs-lookup"><span data-stu-id="1de74-236">at beginning of text or line (m=true)</span></span> |
| $ | <span data-ttu-id="1de74-237">文本结尾（如 \z 而非 \Z）或行尾（m = true）</span><span class="sxs-lookup"><span data-stu-id="1de74-237">at end of text (like \z not \Z) or line (m=true)</span></span> |
| <span data-ttu-id="1de74-238">\A</span><span class="sxs-lookup"><span data-stu-id="1de74-238">\A</span></span> | <span data-ttu-id="1de74-239">文本开头</span><span class="sxs-lookup"><span data-stu-id="1de74-239">at beginning of text</span></span> |
| <span data-ttu-id="1de74-240">\b</span><span class="sxs-lookup"><span data-stu-id="1de74-240">\b</span></span> | <span data-ttu-id="1de74-241">匹配 ASCII 单词边界（\w 表示一端，\W、\A 或 \z 表示另一端）</span><span class="sxs-lookup"><span data-stu-id="1de74-241">at ASCII word boundary (\w on one side and \W, \A, or \z on the other)</span></span> |
| <span data-ttu-id="1de74-242">\B</span><span class="sxs-lookup"><span data-stu-id="1de74-242">\B</span></span> | <span data-ttu-id="1de74-243">匹配非 ASCII 单词边界</span><span class="sxs-lookup"><span data-stu-id="1de74-243">not at ASCII word boundary</span></span> |
| <span data-ttu-id="1de74-244">\g</span><span class="sxs-lookup"><span data-stu-id="1de74-244">\g</span></span> | <span data-ttu-id="1de74-245">匹配正在搜索的从属文本开头（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="1de74-245">at beginning of subtext being searched (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1de74-246">\G</span><span class="sxs-lookup"><span data-stu-id="1de74-246">\G</span></span> | <span data-ttu-id="1de74-247">匹配上一个匹配的结尾（不支持） PERL </span><span class="sxs-lookup"><span data-stu-id="1de74-247">at end of last match (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1de74-248">\Z</span><span class="sxs-lookup"><span data-stu-id="1de74-248">\Z</span></span> | <span data-ttu-id="1de74-249">匹配必须出现在文本末尾，或在文本末尾换行前的位置（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-249">at end of text, or before newline at end of text (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-250">\z</span><span class="sxs-lookup"><span data-stu-id="1de74-250">\z</span></span> | <span data-ttu-id="1de74-251">匹配文本末尾</span><span class="sxs-lookup"><span data-stu-id="1de74-251">at end of text</span></span> |
| <span data-ttu-id="1de74-252">(?=re)</span><span class="sxs-lookup"><span data-stu-id="1de74-252">(?=re)</span></span> | <span data-ttu-id="1de74-253">前向肯定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-253">before text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-254">(?!re)</span><span class="sxs-lookup"><span data-stu-id="1de74-254">(?!re)</span></span> | <span data-ttu-id="1de74-255">前向否定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-255">before text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-256">(?&lt;=re)</span><span class="sxs-lookup"><span data-stu-id="1de74-256">(?&lt;=re)</span></span> | <span data-ttu-id="1de74-257">后向肯定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-257">after text matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-258">(?&lt;!re)</span><span class="sxs-lookup"><span data-stu-id="1de74-258">(?&lt;!re)</span></span> | <span data-ttu-id="1de74-259">后向否定界定符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-259">after text not matching re (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-260">re&amp;</span><span class="sxs-lookup"><span data-stu-id="1de74-260">re&amp;</span></span> | <span data-ttu-id="1de74-261">前向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-261">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-262">re@=</span><span class="sxs-lookup"><span data-stu-id="1de74-262">re@=</span></span> | <span data-ttu-id="1de74-263">前向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-263">before text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-264">re@!</span><span class="sxs-lookup"><span data-stu-id="1de74-264">re@!</span></span> | <span data-ttu-id="1de74-265">前向否定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-265">before text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-266">re@&lt;=</span><span class="sxs-lookup"><span data-stu-id="1de74-266">re@&lt;=</span></span> | <span data-ttu-id="1de74-267">后向肯定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-267">after text matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-268">re@&lt;!</span><span class="sxs-lookup"><span data-stu-id="1de74-268">re@&lt;!</span></span> | <span data-ttu-id="1de74-269">后向否定界定符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-269">after text not matching re (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-270">\zs</span><span class="sxs-lookup"><span data-stu-id="1de74-270">\zs</span></span> | <span data-ttu-id="1de74-271">设置匹配开始（同 \K）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-271">sets start of match (= \K) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-272">\ze</span><span class="sxs-lookup"><span data-stu-id="1de74-272">\ze</span></span> | <span data-ttu-id="1de74-273">设置匹配结尾（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-273">sets end of match (NOT SUPPORTED) VIM</span></span> |
| \%^ | <span data-ttu-id="1de74-274">匹配文件开头（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-274">beginning of file (NOT SUPPORTED) VIM</span></span> |
| \%$ | <span data-ttu-id="1de74-275">匹配文件结尾（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-275">end of file (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-276">\%V</span><span class="sxs-lookup"><span data-stu-id="1de74-276">\%V</span></span> | <span data-ttu-id="1de74-277">在屏幕上匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-277">on screen (NOT SUPPORTED) VIM</span></span> |
| \%# | <span data-ttu-id="1de74-278">从光标位置匹配（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-278">cursor position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-279">\%&#39;m</span><span class="sxs-lookup"><span data-stu-id="1de74-279">\%&#39;m</span></span> | <span data-ttu-id="1de74-280">在标记 m 的位置匹配（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-280">mark m position (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-281">\%23l</span><span class="sxs-lookup"><span data-stu-id="1de74-281">\%23l</span></span> | <span data-ttu-id="1de74-282">在第 23 行匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-282">in line 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-283">\%23c</span><span class="sxs-lookup"><span data-stu-id="1de74-283">\%23c</span></span> | <span data-ttu-id="1de74-284">在第 23 列匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-284">in column 23 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-285">\%23v</span><span class="sxs-lookup"><span data-stu-id="1de74-285">\%23v</span></span> | <span data-ttu-id="1de74-286">在虚拟第 23 列匹配（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-286">in virtual column 23 (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="1de74-287">转义序列</span><span class="sxs-lookup"><span data-stu-id="1de74-287">Escape sequences</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-288">\a</span><span class="sxs-lookup"><span data-stu-id="1de74-288">\a</span></span> | <span data-ttu-id="1de74-289">匹配报警符（等价于 \007）</span><span class="sxs-lookup"><span data-stu-id="1de74-289">bell (≡ \007)</span></span> |
| <span data-ttu-id="1de74-290">\f</span><span class="sxs-lookup"><span data-stu-id="1de74-290">\f</span></span> | <span data-ttu-id="1de74-291">匹配换页符（等价于 \014）</span><span class="sxs-lookup"><span data-stu-id="1de74-291">form feed (≡ \014)</span></span> |
| <span data-ttu-id="1de74-292">\t</span><span class="sxs-lookup"><span data-stu-id="1de74-292">\t</span></span> | <span data-ttu-id="1de74-293">匹配水平制表符（等价于 \011）</span><span class="sxs-lookup"><span data-stu-id="1de74-293">horizontal tab (≡ \011)</span></span> |
| <span data-ttu-id="1de74-294">\n</span><span class="sxs-lookup"><span data-stu-id="1de74-294">\n</span></span> | <span data-ttu-id="1de74-295">匹配换行符（等价于 \012）</span><span class="sxs-lookup"><span data-stu-id="1de74-295">newline (≡ \012)</span></span> |
| <span data-ttu-id="1de74-296">\r</span><span class="sxs-lookup"><span data-stu-id="1de74-296">\r</span></span> | <span data-ttu-id="1de74-297">匹配回车符（等价于 \015）</span><span class="sxs-lookup"><span data-stu-id="1de74-297">carriage return (≡ \015)</span></span> |
| <span data-ttu-id="1de74-298">\v</span><span class="sxs-lookup"><span data-stu-id="1de74-298">\v</span></span> | <span data-ttu-id="1de74-299">匹配垂直制表符（等价于 \013）</span><span class="sxs-lookup"><span data-stu-id="1de74-299">vertical tab character (≡ \013)</span></span> |
| \* | <span data-ttu-id="1de74-300">文本 \*，匹配任意标点字符 \*</span><span class="sxs-lookup"><span data-stu-id="1de74-300">literal \*, for any punctuation character \*</span></span> |
| <span data-ttu-id="1de74-301">\123</span><span class="sxs-lookup"><span data-stu-id="1de74-301">\123</span></span> | <span data-ttu-id="1de74-302">匹配八进制字符代码（最多三位）</span><span class="sxs-lookup"><span data-stu-id="1de74-302">octal character code (up to three digits)</span></span> |
| <span data-ttu-id="1de74-303">\x7F</span><span class="sxs-lookup"><span data-stu-id="1de74-303">\x7F</span></span> | <span data-ttu-id="1de74-304">匹配十六进制字符代码（确定两位）</span><span class="sxs-lookup"><span data-stu-id="1de74-304">hex character code (exactly two digits)</span></span> |
| <span data-ttu-id="1de74-305">\x{10FFFF}</span><span class="sxs-lookup"><span data-stu-id="1de74-305">\x{10FFFF}</span></span> | <span data-ttu-id="1de74-306">匹配十六进制字符代码</span><span class="sxs-lookup"><span data-stu-id="1de74-306">hex character code</span></span> |
| <span data-ttu-id="1de74-307">\C</span><span class="sxs-lookup"><span data-stu-id="1de74-307">\C</span></span> | <span data-ttu-id="1de74-308">匹配单字节，即使在 UTF-8 模式下</span><span class="sxs-lookup"><span data-stu-id="1de74-308">match a single byte even in UTF-8 mode</span></span> |
| <span data-ttu-id="1de74-309">\Q...\E</span><span class="sxs-lookup"><span data-stu-id="1de74-309">\Q...\E</span></span> | <span data-ttu-id="1de74-310">匹配文本 ... 即使 ... 含有标点</span><span class="sxs-lookup"><span data-stu-id="1de74-310">literal text ... even if ... has punctuation</span></span> |
| <span data-ttu-id="1de74-311">\1</span><span class="sxs-lookup"><span data-stu-id="1de74-311">\1</span></span> | <span data-ttu-id="1de74-312">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-312">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-313">\b</span><span class="sxs-lookup"><span data-stu-id="1de74-313">\b</span></span> | <span data-ttu-id="1de74-314">匹配退格 （不支持）（使用 \010）</span><span class="sxs-lookup"><span data-stu-id="1de74-314">backspace (NOT SUPPORTED) (use \010)</span></span> |
| <span data-ttu-id="1de74-315">\cK</span><span class="sxs-lookup"><span data-stu-id="1de74-315">\cK</span></span> | <span data-ttu-id="1de74-316">匹配控制字符 ^K （不支持）（使用 \001 等）</span><span class="sxs-lookup"><span data-stu-id="1de74-316">control char ^K (NOT SUPPORTED) (use \001 etc)</span></span> |
| <span data-ttu-id="1de74-317">\e</span><span class="sxs-lookup"><span data-stu-id="1de74-317">\e</span></span> | <span data-ttu-id="1de74-318">匹配转义符 （不支持）（使用 \033）</span><span class="sxs-lookup"><span data-stu-id="1de74-318">escape (NOT SUPPORTED) (use \033)</span></span> |
| <span data-ttu-id="1de74-319">\g1</span><span class="sxs-lookup"><span data-stu-id="1de74-319">\g1</span></span> | <span data-ttu-id="1de74-320">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-320">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-321">\g{1}</span><span class="sxs-lookup"><span data-stu-id="1de74-321">\g{1}</span></span> | <span data-ttu-id="1de74-322">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-322">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-323">\g{+1}</span><span class="sxs-lookup"><span data-stu-id="1de74-323">\g{+1}</span></span> | <span data-ttu-id="1de74-324">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-324">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-325">\g{-1}</span><span class="sxs-lookup"><span data-stu-id="1de74-325">\g{-1}</span></span> | <span data-ttu-id="1de74-326">匹配反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-326">backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-327">\g{name}</span><span class="sxs-lookup"><span data-stu-id="1de74-327">\g{name}</span></span> | <span data-ttu-id="1de74-328">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-328">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-329">\g&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="1de74-329">\g&lt;name&gt;</span></span> | <span data-ttu-id="1de74-330">匹配子例程调用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-330">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-331">\g&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="1de74-331">\g&#39;name&#39;</span></span> | <span data-ttu-id="1de74-332">匹配子例程调用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-332">subroutine call (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-333">\k&lt;name&gt;</span><span class="sxs-lookup"><span data-stu-id="1de74-333">\k&lt;name&gt;</span></span> | <span data-ttu-id="1de74-334">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-334">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-335">\k&#39;name&#39;</span><span class="sxs-lookup"><span data-stu-id="1de74-335">\k&#39;name&#39;</span></span> | <span data-ttu-id="1de74-336">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-336">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-337">\lX</span><span class="sxs-lookup"><span data-stu-id="1de74-337">\lX</span></span> | <span data-ttu-id="1de74-338">匹配小写 X（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-338">lowercase X (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-339">\ux</span><span class="sxs-lookup"><span data-stu-id="1de74-339">\ux</span></span> | <span data-ttu-id="1de74-340">匹配大写 x（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-340">uppercase x (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-341">\L...\E</span><span class="sxs-lookup"><span data-stu-id="1de74-341">\L...\E</span></span> | <span data-ttu-id="1de74-342">匹配小写文本 ...（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-342">lowercase text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-343">\K</span><span class="sxs-lookup"><span data-stu-id="1de74-343">\K</span></span> | <span data-ttu-id="1de74-344">重置 $0 开头（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-344">reset beginning of $0 (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-345">\N{name}</span><span class="sxs-lookup"><span data-stu-id="1de74-345">\N{name}</span></span> | <span data-ttu-id="1de74-346">匹配已命名 Unicode 字符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-346">named Unicode character (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-347">\R</span><span class="sxs-lookup"><span data-stu-id="1de74-347">\R</span></span> | <span data-ttu-id="1de74-348">匹配换行符（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-348">line break (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-349">\U...\E</span><span class="sxs-lookup"><span data-stu-id="1de74-349">\U...\E</span></span> | <span data-ttu-id="1de74-350">匹配大写文本 ...（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-350">upper case text ... (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-351">\X</span><span class="sxs-lookup"><span data-stu-id="1de74-351">\X</span></span> | <span data-ttu-id="1de74-352">匹配扩展 Unicode 序列（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-352">extended Unicode sequence (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-353">\%d123</span><span class="sxs-lookup"><span data-stu-id="1de74-353">\%d123</span></span> | <span data-ttu-id="1de74-354">匹配十进制字符 123（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-354">decimal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-355">\%xFF</span><span class="sxs-lookup"><span data-stu-id="1de74-355">\%xFF</span></span> | <span data-ttu-id="1de74-356">匹配十六进制字符 FF （不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-356">hex character FF (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-357">\%o123</span><span class="sxs-lookup"><span data-stu-id="1de74-357">\%o123</span></span> | <span data-ttu-id="1de74-358">匹配八进制字符 123（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-358">octal character 123 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-359">\%u1234</span><span class="sxs-lookup"><span data-stu-id="1de74-359">\%u1234</span></span> | <span data-ttu-id="1de74-360">匹配 Unicode 字符 0x1234（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-360">Unicode character 0x1234 (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-361">\%U12345678</span><span class="sxs-lookup"><span data-stu-id="1de74-361">\%U12345678</span></span> | <span data-ttu-id="1de74-362">匹配 Unicode 字符 0x12345678（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-362">Unicode character 0x12345678 (NOT SUPPORTED) VIM</span></span> |

|&nbsp;| <span data-ttu-id="1de74-363">字符组元素</span><span class="sxs-lookup"><span data-stu-id="1de74-363">Character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-364">x</span><span class="sxs-lookup"><span data-stu-id="1de74-364">x</span></span> | <span data-ttu-id="1de74-365">单个字符</span><span class="sxs-lookup"><span data-stu-id="1de74-365">single character</span></span> |
| <span data-ttu-id="1de74-366">A-Z</span><span class="sxs-lookup"><span data-stu-id="1de74-366">A-Z</span></span> | <span data-ttu-id="1de74-367">字符范围（含）</span><span class="sxs-lookup"><span data-stu-id="1de74-367">character range (inclusive)</span></span> |
| <span data-ttu-id="1de74-368">\d</span><span class="sxs-lookup"><span data-stu-id="1de74-368">\d</span></span> | <span data-ttu-id="1de74-369">匹配 Perl 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-369">Perl character class</span></span> |
| <span data-ttu-id="1de74-370">[:foo:]</span><span class="sxs-lookup"><span data-stu-id="1de74-370">[:foo:]</span></span> | <span data-ttu-id="1de74-371">匹配 ASCII 字符组 foo</span><span class="sxs-lookup"><span data-stu-id="1de74-371">ASCII character class foo</span></span> |
| <span data-ttu-id="1de74-372">\p{Foo}</span><span class="sxs-lookup"><span data-stu-id="1de74-372">\p{Foo}</span></span> | <span data-ttu-id="1de74-373">匹配 Unicode 字符组 Foo</span><span class="sxs-lookup"><span data-stu-id="1de74-373">Unicode character class Foo</span></span> |
| <span data-ttu-id="1de74-374">\pF</span><span class="sxs-lookup"><span data-stu-id="1de74-374">\pF</span></span> | <span data-ttu-id="1de74-375">匹配 Unicode 字符组 F（单字母名称）</span><span class="sxs-lookup"><span data-stu-id="1de74-375">Unicode character class F (one-letter name)</span></span> |

|&nbsp;| <span data-ttu-id="1de74-376">作为字符组元素命名的字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-376">Named character classes as character class elements</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-377">[\d]</span><span class="sxs-lookup"><span data-stu-id="1de74-377">[\d]</span></span> | <span data-ttu-id="1de74-378">匹配数字字符（等价于 \d）</span><span class="sxs-lookup"><span data-stu-id="1de74-378">digits (≡ \d)</span></span> |
| <span data-ttu-id="1de74-379">[^\d]</span><span class="sxs-lookup"><span data-stu-id="1de74-379">[^\d]</span></span> | <span data-ttu-id="1de74-380">匹配非数字字符（等价于 \D）</span><span class="sxs-lookup"><span data-stu-id="1de74-380">not digits (≡ \D)</span></span> |
| <span data-ttu-id="1de74-381">[\D]</span><span class="sxs-lookup"><span data-stu-id="1de74-381">[\D]</span></span> | <span data-ttu-id="1de74-382">匹配非数字字符（等价于 \D）</span><span class="sxs-lookup"><span data-stu-id="1de74-382">not digits (≡ \D)</span></span> |
| <span data-ttu-id="1de74-383">[^\D]</span><span class="sxs-lookup"><span data-stu-id="1de74-383">[^\D]</span></span> | <span data-ttu-id="1de74-384">匹配数字字符（等价于 \d）</span><span class="sxs-lookup"><span data-stu-id="1de74-384">not not digits (≡ \d)</span></span> |
| <span data-ttu-id="1de74-385">[[:name:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-385">[[:name:]]</span></span> | <span data-ttu-id="1de74-386">匹配在字符组内部命名的 ASCII 组（等价于 [:name:]）</span><span class="sxs-lookup"><span data-stu-id="1de74-386">named ASCII class inside character class (≡ [:name:])</span></span> |
| <span data-ttu-id="1de74-387">[^[:name:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-387">[^[:name:]]</span></span> | <span data-ttu-id="1de74-388">匹配在排除型字符组内部命名的 ASCII 组（等价于 [:^name:]）</span><span class="sxs-lookup"><span data-stu-id="1de74-388">named ASCII class inside negated character class (≡ [:^name:])</span></span> |
| <span data-ttu-id="1de74-389">[\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="1de74-389">[\p{Name}]</span></span> | <span data-ttu-id="1de74-390">匹配在字符组内部命名的 Unicode 属性（等价于 \p{Name}）</span><span class="sxs-lookup"><span data-stu-id="1de74-390">named Unicode property inside character class (≡ \p{Name})</span></span> |
| <span data-ttu-id="1de74-391">[^\p{Name}]</span><span class="sxs-lookup"><span data-stu-id="1de74-391">[^\p{Name}]</span></span> | <span data-ttu-id="1de74-392">匹配在排除型字符组内部命名的 Unicode 属性（等价于 \P{Name}）</span><span class="sxs-lookup"><span data-stu-id="1de74-392">named Unicode property inside negated character class (≡ \P{Name})</span></span> |

| <a name="user-content-perl"></a> | <span data-ttu-id="1de74-393">Perl 字符组（仅限所有 ASCII 码）</span><span class="sxs-lookup"><span data-stu-id="1de74-393">Perl character classes (all ASCII-only)</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-394">\d</span><span class="sxs-lookup"><span data-stu-id="1de74-394">\d</span></span> | <span data-ttu-id="1de74-395">匹配数字字符（等价于 [0-9]）</span><span class="sxs-lookup"><span data-stu-id="1de74-395">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="1de74-396">\D</span><span class="sxs-lookup"><span data-stu-id="1de74-396">\D</span></span> | <span data-ttu-id="1de74-397">匹配非数字字符（等价于 [^0-9]）</span><span class="sxs-lookup"><span data-stu-id="1de74-397">not digits (≡ [^0-9])</span></span> |
| <span data-ttu-id="1de74-398">\s</span><span class="sxs-lookup"><span data-stu-id="1de74-398">\s</span></span> | <span data-ttu-id="1de74-399">匹配任何空白字符（等价于 [\t\n\f\r]）</span><span class="sxs-lookup"><span data-stu-id="1de74-399">whitespace (≡ [\t\n\f\r])</span></span> |
| <span data-ttu-id="1de74-400">\S</span><span class="sxs-lookup"><span data-stu-id="1de74-400">\S</span></span> | <span data-ttu-id="1de74-401">匹配任何非空白字符（等价于 [^\t\n\f\r]）</span><span class="sxs-lookup"><span data-stu-id="1de74-401">not whitespace (≡ [^\t\n\f\r])</span></span> |
| <span data-ttu-id="1de74-402">\w</span><span class="sxs-lookup"><span data-stu-id="1de74-402">\w</span></span> | <span data-ttu-id="1de74-403">匹配包括下划线的任何单词字符（等价于 [0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="1de74-403">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1de74-404">\W</span><span class="sxs-lookup"><span data-stu-id="1de74-404">\W</span></span> | <span data-ttu-id="1de74-405">匹配任何非单词字符（等价于 [^0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="1de74-405">not word characters (≡ [^0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1de74-406">\h</span><span class="sxs-lookup"><span data-stu-id="1de74-406">\h</span></span> | <span data-ttu-id="1de74-407">匹配水平空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-407">horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-408">\H</span><span class="sxs-lookup"><span data-stu-id="1de74-408">\H</span></span> | <span data-ttu-id="1de74-409">匹配非水平空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-409">not horizontal space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-410">\v</span><span class="sxs-lookup"><span data-stu-id="1de74-410">\v</span></span> | <span data-ttu-id="1de74-411">匹配垂直空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-411">vertical space (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-412">\V</span><span class="sxs-lookup"><span data-stu-id="1de74-412">\V</span></span> | <span data-ttu-id="1de74-413">匹配非垂直空格（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-413">not vertical space (NOT SUPPORTED)</span></span> |

|<a name="user-content-ascii"></a>  | <span data-ttu-id="1de74-414">ASCII 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-414">ASCII character classes</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-415">[[:alnum:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-415">[[:alnum:]]</span></span> | <span data-ttu-id="1de74-416">匹配数字与字母字符（等价于 [0-9A-Za-z]）</span><span class="sxs-lookup"><span data-stu-id="1de74-416">alphanumeric (≡ [0-9A-Za-z])</span></span> |
| <span data-ttu-id="1de74-417">[[:alpha:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-417">[[:alpha:]]</span></span> | <span data-ttu-id="1de74-418">匹配字母字符（等价于 [A-Za-z]）</span><span class="sxs-lookup"><span data-stu-id="1de74-418">alphabetic (≡ [A-Za-z])</span></span> |
| <span data-ttu-id="1de74-419">[[:ascii:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-419">[[:ascii:]]</span></span> | <span data-ttu-id="1de74-420">匹配 ASCII 字符（等价于 [\x00-\x7F]）</span><span class="sxs-lookup"><span data-stu-id="1de74-420">ASCII (≡ [\x00-\x7F])</span></span> |
| <span data-ttu-id="1de74-421">[[:blank:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-421">[[:blank:]]</span></span> | <span data-ttu-id="1de74-422">匹配制表符 （等价于[\t]）</span><span class="sxs-lookup"><span data-stu-id="1de74-422">blank (≡ [\t])</span></span> |
| <span data-ttu-id="1de74-423">[[:cntrl:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-423">[[:cntrl:]]</span></span> | <span data-ttu-id="1de74-424">匹配控制字符（等价于 [\x00-\x1F\x7F]）</span><span class="sxs-lookup"><span data-stu-id="1de74-424">control (≡ [\x00-\x1F\x7F])</span></span> |
| <span data-ttu-id="1de74-425">[[:digit:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-425">[[:digit:]]</span></span> | <span data-ttu-id="1de74-426">匹配数字字符（等价于 [0-9]）</span><span class="sxs-lookup"><span data-stu-id="1de74-426">digits (≡ [0-9])</span></span> |
| <span data-ttu-id="1de74-427">[[:graph:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-427">[[:graph:]]</span></span> | <span data-ttu-id="1de74-428">可打印与可见字符（等价于`[!-~]` 等价于 `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`）</span><span class="sxs-lookup"><span data-stu-id="1de74-428">graphical (≡ `[!-~]` ≡ `[A-Za-z0-9!&quot;#$%&amp;&#39;()\*+,\-./:;&lt;=&gt;?@[\\\]^_`\` `{\|}~]`)</span></span> |
| <span data-ttu-id="1de74-429">[[:lower:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-429">[[:lower:]]</span></span> | <span data-ttu-id="1de74-430">匹配小写字符（等价于 [a-z]）</span><span class="sxs-lookup"><span data-stu-id="1de74-430">lower case (≡ [a-z])</span></span> |
| <span data-ttu-id="1de74-431">[[:print:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-431">[[:print:]]</span></span> | <span data-ttu-id="1de74-432">匹配可打印字符（等价于 [-~] 等价于 [[:graph:]]）</span><span class="sxs-lookup"><span data-stu-id="1de74-432">printable (≡ [-~] ≡ [[:graph:]])</span></span> |
| <span data-ttu-id="1de74-433">[[:punct:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-433">[[:punct:]]</span></span> | <span data-ttu-id="1de74-434">匹配标点字符（等价于 [!-/:-@[-\`{-~]）</span><span class="sxs-lookup"><span data-stu-id="1de74-434">punctuation (≡ [!-/:-@[-\`{-~])</span></span> |
| <span data-ttu-id="1de74-435">[[:space:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-435">[[:space:]]</span></span> | <span data-ttu-id="1de74-436">匹配任何空白字符（等价于 [\t\n\v\f\r]）</span><span class="sxs-lookup"><span data-stu-id="1de74-436">whitespace (≡ [\t\n\v\f\r])</span></span> |
| <span data-ttu-id="1de74-437">[[:upper:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-437">[[:upper:]]</span></span> | <span data-ttu-id="1de74-438">匹配大写字符（等价于 [A-Z] ）</span><span class="sxs-lookup"><span data-stu-id="1de74-438">upper case (≡ [A-Z])</span></span> |
| <span data-ttu-id="1de74-439">[[:word:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-439">[[:word:]]</span></span> | <span data-ttu-id="1de74-440">匹配包括下划线的任何单词字符（等价于 [0-9A-Za-z\_]）</span><span class="sxs-lookup"><span data-stu-id="1de74-440">word characters (≡ [0-9A-Za-z\_])</span></span> |
| <span data-ttu-id="1de74-441">[[:xdigit:]]</span><span class="sxs-lookup"><span data-stu-id="1de74-441">[[:xdigit:]]</span></span> | <span data-ttu-id="1de74-442">匹配十六进制数字字符（等价于 [0-9A-Fa-f]）</span><span class="sxs-lookup"><span data-stu-id="1de74-442">hex digit (≡ [0-9A-Fa-f])</span></span> |

|&nbsp;| <span data-ttu-id="1de74-443">Unicode 字符组名称 - 常规类别</span><span class="sxs-lookup"><span data-stu-id="1de74-443">Unicode character class names--general category</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-444">C</span><span class="sxs-lookup"><span data-stu-id="1de74-444">C</span></span> | <span data-ttu-id="1de74-445">其他</span><span class="sxs-lookup"><span data-stu-id="1de74-445">other</span></span> |
| <span data-ttu-id="1de74-446">抄送</span><span class="sxs-lookup"><span data-stu-id="1de74-446">Cc</span></span> | <span data-ttu-id="1de74-447">control</span><span class="sxs-lookup"><span data-stu-id="1de74-447">control</span></span> |
| <span data-ttu-id="1de74-448">Cf</span><span class="sxs-lookup"><span data-stu-id="1de74-448">Cf</span></span> | <span data-ttu-id="1de74-449">format</span><span class="sxs-lookup"><span data-stu-id="1de74-449">format</span></span> |
| <span data-ttu-id="1de74-450">Cn</span><span class="sxs-lookup"><span data-stu-id="1de74-450">Cn</span></span> | <span data-ttu-id="1de74-451">未赋值（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-451">unassigned code points (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-452">Co</span><span class="sxs-lookup"><span data-stu-id="1de74-452">Co</span></span> | <span data-ttu-id="1de74-453">私用</span><span class="sxs-lookup"><span data-stu-id="1de74-453">private use</span></span> |
| <span data-ttu-id="1de74-454">Cs</span><span class="sxs-lookup"><span data-stu-id="1de74-454">Cs</span></span> | <span data-ttu-id="1de74-455">代理项</span><span class="sxs-lookup"><span data-stu-id="1de74-455">surrogate</span></span> |
| <span data-ttu-id="1de74-456">L</span><span class="sxs-lookup"><span data-stu-id="1de74-456">L</span></span> | <span data-ttu-id="1de74-457">字母</span><span class="sxs-lookup"><span data-stu-id="1de74-457">letter</span></span> |
| <span data-ttu-id="1de74-458">LC</span><span class="sxs-lookup"><span data-stu-id="1de74-458">LC</span></span> | <span data-ttu-id="1de74-459">大小写字母（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-459">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-460">L&amp;</span><span class="sxs-lookup"><span data-stu-id="1de74-460">L&amp;</span></span> | <span data-ttu-id="1de74-461">大小写字母（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-461">cased letter (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-462">Ll</span><span class="sxs-lookup"><span data-stu-id="1de74-462">Ll</span></span> | <span data-ttu-id="1de74-463">小写字母</span><span class="sxs-lookup"><span data-stu-id="1de74-463">lowercase letter</span></span> |
| <span data-ttu-id="1de74-464">Lm</span><span class="sxs-lookup"><span data-stu-id="1de74-464">Lm</span></span> | <span data-ttu-id="1de74-465">修饰字母</span><span class="sxs-lookup"><span data-stu-id="1de74-465">modifier letter</span></span> |
| <span data-ttu-id="1de74-466">Lo</span><span class="sxs-lookup"><span data-stu-id="1de74-466">Lo</span></span> | <span data-ttu-id="1de74-467">其他字母</span><span class="sxs-lookup"><span data-stu-id="1de74-467">other letter</span></span> |
| <span data-ttu-id="1de74-468">Lt</span><span class="sxs-lookup"><span data-stu-id="1de74-468">Lt</span></span> | <span data-ttu-id="1de74-469">首字母大写</span><span class="sxs-lookup"><span data-stu-id="1de74-469">titlecase letter</span></span> |
| <span data-ttu-id="1de74-470">Lu</span><span class="sxs-lookup"><span data-stu-id="1de74-470">Lu</span></span> | <span data-ttu-id="1de74-471">大写字母</span><span class="sxs-lookup"><span data-stu-id="1de74-471">uppercase letter</span></span> |
| <span data-ttu-id="1de74-472">M</span><span class="sxs-lookup"><span data-stu-id="1de74-472">M</span></span> | <span data-ttu-id="1de74-473">标记</span><span class="sxs-lookup"><span data-stu-id="1de74-473">mark</span></span> |
| <span data-ttu-id="1de74-474">Mc</span><span class="sxs-lookup"><span data-stu-id="1de74-474">Mc</span></span> | <span data-ttu-id="1de74-475">间距标记</span><span class="sxs-lookup"><span data-stu-id="1de74-475">spacing mark</span></span> |
| <span data-ttu-id="1de74-476">Me</span><span class="sxs-lookup"><span data-stu-id="1de74-476">Me</span></span> | <span data-ttu-id="1de74-477">封闭标记</span><span class="sxs-lookup"><span data-stu-id="1de74-477">enclosing mark</span></span> |
| <span data-ttu-id="1de74-478">Mn</span><span class="sxs-lookup"><span data-stu-id="1de74-478">Mn</span></span> | <span data-ttu-id="1de74-479">非间距标记</span><span class="sxs-lookup"><span data-stu-id="1de74-479">non-spacing mark</span></span> |
| <span data-ttu-id="1de74-480">N</span><span class="sxs-lookup"><span data-stu-id="1de74-480">N</span></span> | <span data-ttu-id="1de74-481">数字</span><span class="sxs-lookup"><span data-stu-id="1de74-481">number</span></span> |
| <span data-ttu-id="1de74-482">Nd</span><span class="sxs-lookup"><span data-stu-id="1de74-482">Nd</span></span> | <span data-ttu-id="1de74-483">十进制数字</span><span class="sxs-lookup"><span data-stu-id="1de74-483">decimal number</span></span> |
| <span data-ttu-id="1de74-484">Nl</span><span class="sxs-lookup"><span data-stu-id="1de74-484">Nl</span></span> | <span data-ttu-id="1de74-485">字母或数字</span><span class="sxs-lookup"><span data-stu-id="1de74-485">letter number</span></span> |
| <span data-ttu-id="1de74-486">否</span><span class="sxs-lookup"><span data-stu-id="1de74-486">No</span></span> | <span data-ttu-id="1de74-487">其他数字</span><span class="sxs-lookup"><span data-stu-id="1de74-487">other number</span></span> |
| <span data-ttu-id="1de74-488">P</span><span class="sxs-lookup"><span data-stu-id="1de74-488">P</span></span> | <span data-ttu-id="1de74-489">标点符号</span><span class="sxs-lookup"><span data-stu-id="1de74-489">punctuation</span></span> |
| <span data-ttu-id="1de74-490">Pc</span><span class="sxs-lookup"><span data-stu-id="1de74-490">Pc</span></span> | <span data-ttu-id="1de74-491">连接符</span><span class="sxs-lookup"><span data-stu-id="1de74-491">connector punctuation</span></span> |
| <span data-ttu-id="1de74-492">Pd</span><span class="sxs-lookup"><span data-stu-id="1de74-492">Pd</span></span> | <span data-ttu-id="1de74-493">短划线</span><span class="sxs-lookup"><span data-stu-id="1de74-493">dash punctuation</span></span> |
| <span data-ttu-id="1de74-494">Pe</span><span class="sxs-lookup"><span data-stu-id="1de74-494">Pe</span></span> | <span data-ttu-id="1de74-495">结束标点</span><span class="sxs-lookup"><span data-stu-id="1de74-495">close punctuation</span></span> |
| <span data-ttu-id="1de74-496">Pf</span><span class="sxs-lookup"><span data-stu-id="1de74-496">Pf</span></span> | <span data-ttu-id="1de74-497">后引号</span><span class="sxs-lookup"><span data-stu-id="1de74-497">final punctuation</span></span> |
| <span data-ttu-id="1de74-498">Pi</span><span class="sxs-lookup"><span data-stu-id="1de74-498">Pi</span></span> | <span data-ttu-id="1de74-499">前引号</span><span class="sxs-lookup"><span data-stu-id="1de74-499">initial punctuation</span></span> |
| <span data-ttu-id="1de74-500">Po</span><span class="sxs-lookup"><span data-stu-id="1de74-500">Po</span></span> | <span data-ttu-id="1de74-501">其他标点符号</span><span class="sxs-lookup"><span data-stu-id="1de74-501">other punctuation</span></span> |
| <span data-ttu-id="1de74-502">Ps</span><span class="sxs-lookup"><span data-stu-id="1de74-502">Ps</span></span> | <span data-ttu-id="1de74-503">开始标点</span><span class="sxs-lookup"><span data-stu-id="1de74-503">open punctuation</span></span> |
| <span data-ttu-id="1de74-504">S</span><span class="sxs-lookup"><span data-stu-id="1de74-504">S</span></span> | <span data-ttu-id="1de74-505">symbol</span><span class="sxs-lookup"><span data-stu-id="1de74-505">symbol</span></span> |
| <span data-ttu-id="1de74-506">Sc</span><span class="sxs-lookup"><span data-stu-id="1de74-506">Sc</span></span> | <span data-ttu-id="1de74-507">货币符号</span><span class="sxs-lookup"><span data-stu-id="1de74-507">currency symbol</span></span> |
| <span data-ttu-id="1de74-508">Sk</span><span class="sxs-lookup"><span data-stu-id="1de74-508">Sk</span></span> | <span data-ttu-id="1de74-509">修饰符符号</span><span class="sxs-lookup"><span data-stu-id="1de74-509">modifier symbol</span></span> |
| <span data-ttu-id="1de74-510">Sm</span><span class="sxs-lookup"><span data-stu-id="1de74-510">Sm</span></span> | <span data-ttu-id="1de74-511">数学符号</span><span class="sxs-lookup"><span data-stu-id="1de74-511">math symbol</span></span> |
| <span data-ttu-id="1de74-512">So</span><span class="sxs-lookup"><span data-stu-id="1de74-512">So</span></span> | <span data-ttu-id="1de74-513">其他符号</span><span class="sxs-lookup"><span data-stu-id="1de74-513">other symbol</span></span> |
| <span data-ttu-id="1de74-514">Z</span><span class="sxs-lookup"><span data-stu-id="1de74-514">Z</span></span> | <span data-ttu-id="1de74-515">分隔符</span><span class="sxs-lookup"><span data-stu-id="1de74-515">separator</span></span> |
| <span data-ttu-id="1de74-516">Zl</span><span class="sxs-lookup"><span data-stu-id="1de74-516">Zl</span></span> | <span data-ttu-id="1de74-517">行分隔符</span><span class="sxs-lookup"><span data-stu-id="1de74-517">line separator</span></span> |
| <span data-ttu-id="1de74-518">Zp</span><span class="sxs-lookup"><span data-stu-id="1de74-518">Zp</span></span> | <span data-ttu-id="1de74-519">段落分隔符</span><span class="sxs-lookup"><span data-stu-id="1de74-519">paragraph separator</span></span> |
| <span data-ttu-id="1de74-520">Zs</span><span class="sxs-lookup"><span data-stu-id="1de74-520">Zs</span></span> | <span data-ttu-id="1de74-521">空白分隔符</span><span class="sxs-lookup"><span data-stu-id="1de74-521">space separator</span></span> |

| <span data-ttu-id="1de74-522">Unicode 字符组名称 - 文字系统</span><span class="sxs-lookup"><span data-stu-id="1de74-522">Unicode character class names--scripts</span></span> |
| --- |
| <span data-ttu-id="1de74-523">阿德拉姆</span><span class="sxs-lookup"><span data-stu-id="1de74-523">Adlam</span></span> |
| <span data-ttu-id="1de74-524">阿霍姆语</span><span class="sxs-lookup"><span data-stu-id="1de74-524">Ahom</span></span> |
| <span data-ttu-id="1de74-525">安纳托利亚 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="1de74-525">Anatolian\_Hieroglyphs</span></span> |
| <span data-ttu-id="1de74-526">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="1de74-526">Arabic</span></span> |
| <span data-ttu-id="1de74-527">亚美尼亚语</span><span class="sxs-lookup"><span data-stu-id="1de74-527">Armenian</span></span> |
| <span data-ttu-id="1de74-528">阿维斯陀语</span><span class="sxs-lookup"><span data-stu-id="1de74-528">Avestan</span></span> |
| <span data-ttu-id="1de74-529">巴厘文</span><span class="sxs-lookup"><span data-stu-id="1de74-529">Balinese</span></span> |
| <span data-ttu-id="1de74-530">巴姆穆文</span><span class="sxs-lookup"><span data-stu-id="1de74-530">Bamum</span></span> |
| <span data-ttu-id="1de74-531">Bassa\_Vah</span><span class="sxs-lookup"><span data-stu-id="1de74-531">Bassa\_Vah</span></span> |
| <span data-ttu-id="1de74-532">巴塔克文</span><span class="sxs-lookup"><span data-stu-id="1de74-532">Batak</span></span> |
| <span data-ttu-id="1de74-533">孟加拉语</span><span class="sxs-lookup"><span data-stu-id="1de74-533">Bengali</span></span> |
| <span data-ttu-id="1de74-534">拜克舒克文</span><span class="sxs-lookup"><span data-stu-id="1de74-534">Bhaiksuki</span></span> |
| <span data-ttu-id="1de74-535">汉语拼音字母</span><span class="sxs-lookup"><span data-stu-id="1de74-535">Bopomofo</span></span> |
| <span data-ttu-id="1de74-536">婆罗米文</span><span class="sxs-lookup"><span data-stu-id="1de74-536">Brahmi</span></span> |
| <span data-ttu-id="1de74-537">布莱叶盲文</span><span class="sxs-lookup"><span data-stu-id="1de74-537">Braille</span></span> |
| <span data-ttu-id="1de74-538">布吉文</span><span class="sxs-lookup"><span data-stu-id="1de74-538">Buginese</span></span> |
| <span data-ttu-id="1de74-539">布锡语</span><span class="sxs-lookup"><span data-stu-id="1de74-539">Buhid</span></span> |
| <span data-ttu-id="1de74-540">加拿大 \_ 澳大利亚土著语</span><span class="sxs-lookup"><span data-stu-id="1de74-540">Canadian\_Aboriginal</span></span> |
| <span data-ttu-id="1de74-541">卡里亚文</span><span class="sxs-lookup"><span data-stu-id="1de74-541">Carian</span></span> |
| <span data-ttu-id="1de74-542">高加索 \_ 阿尔巴尼亚语</span><span class="sxs-lookup"><span data-stu-id="1de74-542">Caucasian\_Albanian</span></span> |
| <span data-ttu-id="1de74-543">占文</span><span class="sxs-lookup"><span data-stu-id="1de74-543">Chakma</span></span> |
| <span data-ttu-id="1de74-544">Cham</span><span class="sxs-lookup"><span data-stu-id="1de74-544">Cham</span></span> |
| <span data-ttu-id="1de74-545">切罗基语</span><span class="sxs-lookup"><span data-stu-id="1de74-545">Cherokee</span></span> |
| <span data-ttu-id="1de74-546">花剌子模语</span><span class="sxs-lookup"><span data-stu-id="1de74-546">Chorasmian</span></span> |
| <span data-ttu-id="1de74-547">通用</span><span class="sxs-lookup"><span data-stu-id="1de74-547">Common</span></span> |
| <span data-ttu-id="1de74-548">科普特语</span><span class="sxs-lookup"><span data-stu-id="1de74-548">Coptic</span></span> |
| <span data-ttu-id="1de74-549">楔形文字</span><span class="sxs-lookup"><span data-stu-id="1de74-549">Cuneiform</span></span> |
| <span data-ttu-id="1de74-550">塞浦路斯语</span><span class="sxs-lookup"><span data-stu-id="1de74-550">Cypriot</span></span> |
| <span data-ttu-id="1de74-551">西里尔字母</span><span class="sxs-lookup"><span data-stu-id="1de74-551">Cyrillic</span></span> |
| <span data-ttu-id="1de74-552">德塞莱特文</span><span class="sxs-lookup"><span data-stu-id="1de74-552">Deseret</span></span> |
| <span data-ttu-id="1de74-553">梵文</span><span class="sxs-lookup"><span data-stu-id="1de74-553">Devanagari</span></span> |
| <span data-ttu-id="1de74-554">Dives \_ Akuru</span><span class="sxs-lookup"><span data-stu-id="1de74-554">Dives\_Akuru</span></span> |
| <span data-ttu-id="1de74-555">多格兰语</span><span class="sxs-lookup"><span data-stu-id="1de74-555">Dogra</span></span> |
| <span data-ttu-id="1de74-556">杜普洛伊速记体</span><span class="sxs-lookup"><span data-stu-id="1de74-556">Duployan</span></span> |
| <span data-ttu-id="1de74-557">埃及 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="1de74-557">Egyptian\_Hieroglyphs</span></span> |
| <span data-ttu-id="1de74-558">爱尔巴桑语</span><span class="sxs-lookup"><span data-stu-id="1de74-558">Elbasan</span></span> |
| <span data-ttu-id="1de74-559">埃利迈语</span><span class="sxs-lookup"><span data-stu-id="1de74-559">Elymaic</span></span> |
| <span data-ttu-id="1de74-560">埃塞俄比亚文</span><span class="sxs-lookup"><span data-stu-id="1de74-560">Ethiopic</span></span> |
| <span data-ttu-id="1de74-561">格鲁吉亚语</span><span class="sxs-lookup"><span data-stu-id="1de74-561">Georgian</span></span> |
| <span data-ttu-id="1de74-562">格拉哥里语</span><span class="sxs-lookup"><span data-stu-id="1de74-562">Glagolitic</span></span> |
| <span data-ttu-id="1de74-563">哥特语</span><span class="sxs-lookup"><span data-stu-id="1de74-563">Gothic</span></span> |
| <span data-ttu-id="1de74-564">格兰塔字母</span><span class="sxs-lookup"><span data-stu-id="1de74-564">Grantha</span></span> |
| <span data-ttu-id="1de74-565">希腊语</span><span class="sxs-lookup"><span data-stu-id="1de74-565">Greek</span></span> |
| <span data-ttu-id="1de74-566">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="1de74-566">Gujarati</span></span> |
| <span data-ttu-id="1de74-567">Gunjala \_Gondi</span><span class="sxs-lookup"><span data-stu-id="1de74-567">Gunjala\_Gondi</span></span> |
| <span data-ttu-id="1de74-568">锡克教文</span><span class="sxs-lookup"><span data-stu-id="1de74-568">Gurmukhi</span></span> |
| <span data-ttu-id="1de74-569">汉语</span><span class="sxs-lookup"><span data-stu-id="1de74-569">Han</span></span> |
| <span data-ttu-id="1de74-570">韩语</span><span class="sxs-lookup"><span data-stu-id="1de74-570">Hangul</span></span> |
| <span data-ttu-id="1de74-571">Hanifi \ _Rohingya</span><span class="sxs-lookup"><span data-stu-id="1de74-571">Hanifi\_Rohingya</span></span> |
| <span data-ttu-id="1de74-572">汉奴劳族文</span><span class="sxs-lookup"><span data-stu-id="1de74-572">Hanunoo</span></span> |
| <span data-ttu-id="1de74-573">哈特兰文</span><span class="sxs-lookup"><span data-stu-id="1de74-573">Hatran</span></span> |
| <span data-ttu-id="1de74-574">希伯来语</span><span class="sxs-lookup"><span data-stu-id="1de74-574">Hebrew</span></span> |
| <span data-ttu-id="1de74-575">日文</span><span class="sxs-lookup"><span data-stu-id="1de74-575">Hiragana</span></span> |
| <span data-ttu-id="1de74-576">英制文字 \_ 阿拉姆语</span><span class="sxs-lookup"><span data-stu-id="1de74-576">Imperial\_Aramaic</span></span> |
| <span data-ttu-id="1de74-577">继承</span><span class="sxs-lookup"><span data-stu-id="1de74-577">Inherited</span></span> |
| <span data-ttu-id="1de74-578">碑文 \_ 巴拉维语</span><span class="sxs-lookup"><span data-stu-id="1de74-578">Inscriptional\_Pahlavi</span></span> |
| <span data-ttu-id="1de74-579">碑文 \_ 帕提亚语</span><span class="sxs-lookup"><span data-stu-id="1de74-579">Inscriptional\_Parthian</span></span> |
| <span data-ttu-id="1de74-580">爪哇文</span><span class="sxs-lookup"><span data-stu-id="1de74-580">Javanese</span></span> |
| <span data-ttu-id="1de74-581">凯提文</span><span class="sxs-lookup"><span data-stu-id="1de74-581">Kaithi</span></span> |
| <span data-ttu-id="1de74-582">埃纳德语</span><span class="sxs-lookup"><span data-stu-id="1de74-582">Kannada</span></span> |
| <span data-ttu-id="1de74-583">片假名</span><span class="sxs-lookup"><span data-stu-id="1de74-583">Katakana</span></span> |
| <span data-ttu-id="1de74-584">克耶 \_ 列支敦士登</span><span class="sxs-lookup"><span data-stu-id="1de74-584">Kayah\_Li</span></span> |
| <span data-ttu-id="1de74-585">卡罗须提文</span><span class="sxs-lookup"><span data-stu-id="1de74-585">Kharoshthi</span></span> |
| <span data-ttu-id="1de74-586">契丹 \_小\_文字</span><span class="sxs-lookup"><span data-stu-id="1de74-586">Khitan\_Small\_Script</span></span> |
| <span data-ttu-id="1de74-587">高棉语</span><span class="sxs-lookup"><span data-stu-id="1de74-587">Khmer</span></span> |
| <span data-ttu-id="1de74-588">克吉奇文</span><span class="sxs-lookup"><span data-stu-id="1de74-588">Khojki</span></span> |
| <span data-ttu-id="1de74-589">信德文</span><span class="sxs-lookup"><span data-stu-id="1de74-589">Khudawadi</span></span> |
| <span data-ttu-id="1de74-590">老挝语</span><span class="sxs-lookup"><span data-stu-id="1de74-590">Lao</span></span> |
| <span data-ttu-id="1de74-591">拉丁语</span><span class="sxs-lookup"><span data-stu-id="1de74-591">Latin</span></span> |
| <span data-ttu-id="1de74-592">雷布查文</span><span class="sxs-lookup"><span data-stu-id="1de74-592">Lepcha</span></span> |
| <span data-ttu-id="1de74-593">林布文</span><span class="sxs-lookup"><span data-stu-id="1de74-593">Limbu</span></span> |
| <span data-ttu-id="1de74-594">线性 \_A</span><span class="sxs-lookup"><span data-stu-id="1de74-594">Linear\_A</span></span> |
| <span data-ttu-id="1de74-595">线性 \_B</span><span class="sxs-lookup"><span data-stu-id="1de74-595">Linear\_B</span></span> |
| <span data-ttu-id="1de74-596">僳文傈</span><span class="sxs-lookup"><span data-stu-id="1de74-596">Lisu</span></span> |
| <span data-ttu-id="1de74-597">利西亚文</span><span class="sxs-lookup"><span data-stu-id="1de74-597">Lycian</span></span> |
| <span data-ttu-id="1de74-598">吕底亚文</span><span class="sxs-lookup"><span data-stu-id="1de74-598">Lydian</span></span> |
| <span data-ttu-id="1de74-599">马哈詹语</span><span class="sxs-lookup"><span data-stu-id="1de74-599">Mahajani</span></span> |
| <span data-ttu-id="1de74-600">望加锡语</span><span class="sxs-lookup"><span data-stu-id="1de74-600">Makasar</span></span> |
| <span data-ttu-id="1de74-601">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="1de74-601">Malayalam</span></span> |
| <span data-ttu-id="1de74-602">阿拉米文</span><span class="sxs-lookup"><span data-stu-id="1de74-602">Mandaic</span></span> |
| <span data-ttu-id="1de74-603">摩尼文</span><span class="sxs-lookup"><span data-stu-id="1de74-603">Manichaean</span></span> |
| <span data-ttu-id="1de74-604">Marchen</span><span class="sxs-lookup"><span data-stu-id="1de74-604">Marchen</span></span> |
| <span data-ttu-id="1de74-605">Masaram\_Gondi</span><span class="sxs-lookup"><span data-stu-id="1de74-605">Masaram\_Gondi</span></span> |
| <span data-ttu-id="1de74-606">梅德法伊德林文</span><span class="sxs-lookup"><span data-stu-id="1de74-606">Medefaidrin</span></span> |
| <span data-ttu-id="1de74-607">梅泰族 \_ 曼尼普尔文</span><span class="sxs-lookup"><span data-stu-id="1de74-607">Meetei\_Mayek</span></span> |
| <span data-ttu-id="1de74-608">门德 \_ 门迪文</span><span class="sxs-lookup"><span data-stu-id="1de74-608">Mende\_Kikakui</span></span> |
| <span data-ttu-id="1de74-609">麦罗埃 \_ 手写体</span><span class="sxs-lookup"><span data-stu-id="1de74-609">Meroitic\_Cursive</span></span> |
| <span data-ttu-id="1de74-610">麦罗埃 \_ 象形文字</span><span class="sxs-lookup"><span data-stu-id="1de74-610">Meroitic\_Hieroglyphs</span></span> |
| <span data-ttu-id="1de74-611">苗文</span><span class="sxs-lookup"><span data-stu-id="1de74-611">Miao</span></span> |
| <span data-ttu-id="1de74-612">莫迪文</span><span class="sxs-lookup"><span data-stu-id="1de74-612">Modi</span></span> |
| <span data-ttu-id="1de74-613">蒙古语</span><span class="sxs-lookup"><span data-stu-id="1de74-613">Mongolian</span></span> |
| <span data-ttu-id="1de74-614">毛里塔尼亚乌吉亚</span><span class="sxs-lookup"><span data-stu-id="1de74-614">Mro</span></span> |
| <span data-ttu-id="1de74-615">穆尔塔尼</span><span class="sxs-lookup"><span data-stu-id="1de74-615">Multani</span></span> |
| <span data-ttu-id="1de74-616">缅甸</span><span class="sxs-lookup"><span data-stu-id="1de74-616">Myanmar</span></span> |
| <span data-ttu-id="1de74-617">纳巴泰</span><span class="sxs-lookup"><span data-stu-id="1de74-617">Nabataean</span></span> |
| <span data-ttu-id="1de74-618">楠迪梵文</span><span class="sxs-lookup"><span data-stu-id="1de74-618">Nandinagari</span></span> |
| <span data-ttu-id="1de74-619">New\_Tai\_Lue</span><span class="sxs-lookup"><span data-stu-id="1de74-619">New\_Tai\_Lue</span></span> |
| <span data-ttu-id="1de74-620">印度比哈尔邦</span><span class="sxs-lookup"><span data-stu-id="1de74-620">Newa</span></span> |
| <span data-ttu-id="1de74-621">Nko</span><span class="sxs-lookup"><span data-stu-id="1de74-621">Nko</span></span> |
| <span data-ttu-id="1de74-622">女书</span><span class="sxs-lookup"><span data-stu-id="1de74-622">Nushu</span></span> |
| <span data-ttu-id="1de74-623">Nyiakeng \ _Puachue \ _Hmong</span><span class="sxs-lookup"><span data-stu-id="1de74-623">Nyiakeng\_Puachue\_Hmong</span></span> |
| <span data-ttu-id="1de74-624">欧甘字母</span><span class="sxs-lookup"><span data-stu-id="1de74-624">Ogham</span></span> |
| <span data-ttu-id="1de74-625">Ol\_Chiki</span><span class="sxs-lookup"><span data-stu-id="1de74-625">Ol\_Chiki</span></span> |
| <span data-ttu-id="1de74-626">古语 \_ 匈牙利语</span><span class="sxs-lookup"><span data-stu-id="1de74-626">Old\_Hungarian</span></span> |
| <span data-ttu-id="1de74-627">古语 \_ 意大利语</span><span class="sxs-lookup"><span data-stu-id="1de74-627">Old\_Italic</span></span> |
| <span data-ttu-id="1de74-628">古语 \_ 北部 \_ 阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="1de74-628">Old\_North\_Arabian</span></span> |
| <span data-ttu-id="1de74-629">古语 \_ 彼尔姆语</span><span class="sxs-lookup"><span data-stu-id="1de74-629">Old\_Permic</span></span> |
| <span data-ttu-id="1de74-630">古语 \_ 波斯语</span><span class="sxs-lookup"><span data-stu-id="1de74-630">Old\_Persian</span></span> |
| <span data-ttu-id="1de74-631">古语 \_ 古索格代亚纳语</span><span class="sxs-lookup"><span data-stu-id="1de74-631">Old\_Sogdian</span></span> |
| <span data-ttu-id="1de74-632">古语 \_ 南部 \_ 阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="1de74-632">Old\_South\_Arabian</span></span> |
| <span data-ttu-id="1de74-633">古语 \_ 突厥语</span><span class="sxs-lookup"><span data-stu-id="1de74-633">Old\_Turkic</span></span> |
| <span data-ttu-id="1de74-634">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="1de74-634">Oriya</span></span> |
| <span data-ttu-id="1de74-635">欧塞奇语</span><span class="sxs-lookup"><span data-stu-id="1de74-635">Osage</span></span> |
| <span data-ttu-id="1de74-636">奥斯曼亚字母</span><span class="sxs-lookup"><span data-stu-id="1de74-636">Osmanya</span></span> |
| <span data-ttu-id="1de74-637">救世苗文 \_ 苗语</span><span class="sxs-lookup"><span data-stu-id="1de74-637">Pahawh\_Hmong</span></span> |
| <span data-ttu-id="1de74-638">帕米拉语</span><span class="sxs-lookup"><span data-stu-id="1de74-638">Palmyrene</span></span> |
| <span data-ttu-id="1de74-639">Pau\_Cin\_Hau</span><span class="sxs-lookup"><span data-stu-id="1de74-639">Pau\_Cin\_Hau</span></span> |
| <span data-ttu-id="1de74-640">Phags\_Pa</span><span class="sxs-lookup"><span data-stu-id="1de74-640">Phags\_Pa</span></span> |
| <span data-ttu-id="1de74-641">腓尼基语</span><span class="sxs-lookup"><span data-stu-id="1de74-641">Phoenician</span></span> |
| <span data-ttu-id="1de74-642">Psalter \ _Pahlavi</span><span class="sxs-lookup"><span data-stu-id="1de74-642">Psalter\_Pahlavi</span></span> |
| <span data-ttu-id="1de74-643">勒姜语</span><span class="sxs-lookup"><span data-stu-id="1de74-643">Rejang</span></span> |
| <span data-ttu-id="1de74-644">古北欧文字</span><span class="sxs-lookup"><span data-stu-id="1de74-644">Runic</span></span> |
| <span data-ttu-id="1de74-645">撒马利亚文</span><span class="sxs-lookup"><span data-stu-id="1de74-645">Samaritan</span></span> |
| <span data-ttu-id="1de74-646">索拉什特拉文</span><span class="sxs-lookup"><span data-stu-id="1de74-646">Saurashtra</span></span> |
| <span data-ttu-id="1de74-647">夏拉达文</span><span class="sxs-lookup"><span data-stu-id="1de74-647">Sharada</span></span> |
| <span data-ttu-id="1de74-648">萧伯纳文</span><span class="sxs-lookup"><span data-stu-id="1de74-648">Shavian</span></span> |
| <span data-ttu-id="1de74-649">悉昙文字</span><span class="sxs-lookup"><span data-stu-id="1de74-649">Siddham</span></span> |
| <span data-ttu-id="1de74-650">手语书写体</span><span class="sxs-lookup"><span data-stu-id="1de74-650">SignWriting</span></span> |
| <span data-ttu-id="1de74-651">僧伽罗语</span><span class="sxs-lookup"><span data-stu-id="1de74-651">Sinhala</span></span> |
| <span data-ttu-id="1de74-652">粟特语</span><span class="sxs-lookup"><span data-stu-id="1de74-652">Sogdian</span></span> |
| <span data-ttu-id="1de74-653">Sora\_Sompeng</span><span class="sxs-lookup"><span data-stu-id="1de74-653">Sora\_Sompeng</span></span> |
| <span data-ttu-id="1de74-654">索永布语</span><span class="sxs-lookup"><span data-stu-id="1de74-654">Soyombo</span></span> |
| <span data-ttu-id="1de74-655">巽他语</span><span class="sxs-lookup"><span data-stu-id="1de74-655">Sundanese</span></span> |
| <span data-ttu-id="1de74-656">Syloti\_Nagri</span><span class="sxs-lookup"><span data-stu-id="1de74-656">Syloti\_Nagri</span></span> |
| <span data-ttu-id="1de74-657">叙利亚语</span><span class="sxs-lookup"><span data-stu-id="1de74-657">Syriac</span></span> |
| <span data-ttu-id="1de74-658">他加禄语</span><span class="sxs-lookup"><span data-stu-id="1de74-658">Tagalog</span></span> |
| <span data-ttu-id="1de74-659">塔班瓦语</span><span class="sxs-lookup"><span data-stu-id="1de74-659">Tagbanwa</span></span> |
| <span data-ttu-id="1de74-660">Tai\_Le</span><span class="sxs-lookup"><span data-stu-id="1de74-660">Tai\_Le</span></span> |
| <span data-ttu-id="1de74-661">Tai\_Tham</span><span class="sxs-lookup"><span data-stu-id="1de74-661">Tai\_Tham</span></span> |
| <span data-ttu-id="1de74-662">Tai\_Viet</span><span class="sxs-lookup"><span data-stu-id="1de74-662">Tai\_Viet</span></span> |
| <span data-ttu-id="1de74-663">泰克里文</span><span class="sxs-lookup"><span data-stu-id="1de74-663">Takri</span></span> |
| <span data-ttu-id="1de74-664">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="1de74-664">Tamil</span></span> |
| <span data-ttu-id="1de74-665">西夏语</span><span class="sxs-lookup"><span data-stu-id="1de74-665">Tangut</span></span> |
| <span data-ttu-id="1de74-666">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="1de74-666">Telugu</span></span> |
| <span data-ttu-id="1de74-667">它拿字母</span><span class="sxs-lookup"><span data-stu-id="1de74-667">Thaana</span></span> |
| <span data-ttu-id="1de74-668">泰语</span><span class="sxs-lookup"><span data-stu-id="1de74-668">Thai</span></span> |
| <span data-ttu-id="1de74-669">藏语</span><span class="sxs-lookup"><span data-stu-id="1de74-669">Tibetan</span></span> |
| <span data-ttu-id="1de74-670">提夫纳语</span><span class="sxs-lookup"><span data-stu-id="1de74-670">Tifinagh</span></span> |
| <span data-ttu-id="1de74-671">底罗仆多文</span><span class="sxs-lookup"><span data-stu-id="1de74-671">Tirhuta</span></span> |
| <span data-ttu-id="1de74-672">乌加里特语</span><span class="sxs-lookup"><span data-stu-id="1de74-672">Ugaritic</span></span> |
| <span data-ttu-id="1de74-673">瓦依语</span><span class="sxs-lookup"><span data-stu-id="1de74-673">Vai</span></span> |
| <span data-ttu-id="1de74-674">万秋文</span><span class="sxs-lookup"><span data-stu-id="1de74-674">Wancho</span></span> |
| <span data-ttu-id="1de74-675">Warang\_Citi</span><span class="sxs-lookup"><span data-stu-id="1de74-675">Warang\_Citi</span></span> |
| <span data-ttu-id="1de74-676">雅兹迪语</span><span class="sxs-lookup"><span data-stu-id="1de74-676">Yezidi</span></span> |
| <span data-ttu-id="1de74-677">彝语</span><span class="sxs-lookup"><span data-stu-id="1de74-677">Yi</span></span> |
| <span data-ttu-id="1de74-678">Zanabazar\_Square</span><span class="sxs-lookup"><span data-stu-id="1de74-678">Zanabazar\_Square</span></span> |

|&nbsp;| <span data-ttu-id="1de74-679">Vim 字符组</span><span class="sxs-lookup"><span data-stu-id="1de74-679">Vim character classes</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-680">\i</span><span class="sxs-lookup"><span data-stu-id="1de74-680">\i</span></span> | <span data-ttu-id="1de74-681">匹配标识符字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-681">identifier character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-682">\I</span><span class="sxs-lookup"><span data-stu-id="1de74-682">\I</span></span> | <span data-ttu-id="1de74-683">\i 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-683">\i except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-684">\k</span><span class="sxs-lookup"><span data-stu-id="1de74-684">\k</span></span> | <span data-ttu-id="1de74-685">匹配关键字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-685">keyword character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-686">\K</span><span class="sxs-lookup"><span data-stu-id="1de74-686">\K</span></span> | <span data-ttu-id="1de74-687">\k 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-687">\k except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-688">\f</span><span class="sxs-lookup"><span data-stu-id="1de74-688">\f</span></span> | <span data-ttu-id="1de74-689">匹配文件名称字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-689">file name character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-690">\F</span><span class="sxs-lookup"><span data-stu-id="1de74-690">\F</span></span> | <span data-ttu-id="1de74-691">\f 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-691">\f except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-692">\p</span><span class="sxs-lookup"><span data-stu-id="1de74-692">\p</span></span> | <span data-ttu-id="1de74-693">匹配可打印字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-693">printable character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-694">\P</span><span class="sxs-lookup"><span data-stu-id="1de74-694">\P</span></span> | <span data-ttu-id="1de74-695">\p 不包括数字字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-695">\p except digits (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-696">\s</span><span class="sxs-lookup"><span data-stu-id="1de74-696">\s</span></span> | <span data-ttu-id="1de74-697">匹配空白字符（等价于 [\t]）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-697">whitespace character (≡ [\t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-698">\S</span><span class="sxs-lookup"><span data-stu-id="1de74-698">\S</span></span> | <span data-ttu-id="1de74-699">匹配非空白字符（等价于 [\t]）（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-699">non-white space character (≡ [^ \t]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-700">\d</span><span class="sxs-lookup"><span data-stu-id="1de74-700">\d</span></span> | <span data-ttu-id="1de74-701">匹配数字字符（等价于 [0-9]）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-701">digits (≡ [0-9]) VIM</span></span> |
| <span data-ttu-id="1de74-702">\D</span><span class="sxs-lookup"><span data-stu-id="1de74-702">\D</span></span> | <span data-ttu-id="1de74-703">非 \d VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-703">not \d VIM</span></span> |
| <span data-ttu-id="1de74-704">\x</span><span class="sxs-lookup"><span data-stu-id="1de74-704">\x</span></span> | <span data-ttu-id="1de74-705">匹配十六进制数字字符（等价于 [0-9A-Fa-f]）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-705">hex digits (≡ [0-9A-Fa-f]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-706">\X</span><span class="sxs-lookup"><span data-stu-id="1de74-706">\X</span></span> | <span data-ttu-id="1de74-707">非 \x（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-707">not \x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-708">\o</span><span class="sxs-lookup"><span data-stu-id="1de74-708">\o</span></span> | <span data-ttu-id="1de74-709">匹配八进制数字字符（等价于 [0-7]）（不支持） VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-709">octal digits (≡ [0-7]) (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-710">\O</span><span class="sxs-lookup"><span data-stu-id="1de74-710">\O</span></span> | <span data-ttu-id="1de74-711">非 \o（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-711">not \o (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-712">\w</span><span class="sxs-lookup"><span data-stu-id="1de74-712">\w</span></span> | <span data-ttu-id="1de74-713">匹配单词字符 VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-713">word character VIM</span></span> |
| <span data-ttu-id="1de74-714">\W</span><span class="sxs-lookup"><span data-stu-id="1de74-714">\W</span></span> | <span data-ttu-id="1de74-715">非 \w VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-715">not \w VIM</span></span> |
| <span data-ttu-id="1de74-716">\h</span><span class="sxs-lookup"><span data-stu-id="1de74-716">\h</span></span> | <span data-ttu-id="1de74-717">匹配单词起始字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-717">head of word character (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-718">\H</span><span class="sxs-lookup"><span data-stu-id="1de74-718">\H</span></span> | <span data-ttu-id="1de74-719">非 \h（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-719">not \h (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-720">\a</span><span class="sxs-lookup"><span data-stu-id="1de74-720">\a</span></span> | <span data-ttu-id="1de74-721">匹配字母字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-721">alphabetic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-722">\A</span><span class="sxs-lookup"><span data-stu-id="1de74-722">\A</span></span> | <span data-ttu-id="1de74-723">非 \a（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-723">not \a (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-724">\l</span><span class="sxs-lookup"><span data-stu-id="1de74-724">\l</span></span> | <span data-ttu-id="1de74-725">匹配小写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-725">lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-726">\L</span><span class="sxs-lookup"><span data-stu-id="1de74-726">\L</span></span> | <span data-ttu-id="1de74-727">匹配非小写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-727">not lowercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-728">\u</span><span class="sxs-lookup"><span data-stu-id="1de74-728">\u</span></span> | <span data-ttu-id="1de74-729">匹配大写字符（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-729">uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-730">\U</span><span class="sxs-lookup"><span data-stu-id="1de74-730">\U</span></span> | <span data-ttu-id="1de74-731">匹配非大写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-731">not uppercase (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-732">\_x</span><span class="sxs-lookup"><span data-stu-id="1de74-732">\_x</span></span> | <span data-ttu-id="1de74-733">\x 加上换行符，匹配任意 x（不支持） VIM </span><span class="sxs-lookup"><span data-stu-id="1de74-733">\x plus newline, for any x (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-734">\c</span><span class="sxs-lookup"><span data-stu-id="1de74-734">\c</span></span> | <span data-ttu-id="1de74-735">忽略大小写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-735">ignore case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-736">\C</span><span class="sxs-lookup"><span data-stu-id="1de74-736">\C</span></span> | <span data-ttu-id="1de74-737">匹配大小写（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-737">match case (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-738">\m</span><span class="sxs-lookup"><span data-stu-id="1de74-738">\m</span></span> | <span data-ttu-id="1de74-739">magic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-739">magic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-740">\M</span><span class="sxs-lookup"><span data-stu-id="1de74-740">\M</span></span> | <span data-ttu-id="1de74-741">nomagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-741">nomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-742">\v</span><span class="sxs-lookup"><span data-stu-id="1de74-742">\v</span></span> | <span data-ttu-id="1de74-743">verymagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-743">verymagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-744">\V</span><span class="sxs-lookup"><span data-stu-id="1de74-744">\V</span></span> | <span data-ttu-id="1de74-745">verynomagic（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-745">verynomagic (NOT SUPPORTED) VIM</span></span> |
| <span data-ttu-id="1de74-746">\Z</span><span class="sxs-lookup"><span data-stu-id="1de74-746">\Z</span></span> | <span data-ttu-id="1de74-747">忽略 Unicode 组合字符的不同（不支持）VIM</span><span class="sxs-lookup"><span data-stu-id="1de74-747">ignore differences in Unicode combining characters (NOT SUPPORTED) VIM</span></span> |

| &nbsp; | <span data-ttu-id="1de74-748">Magic</span><span class="sxs-lookup"><span data-stu-id="1de74-748">Magic</span></span> |
| --- | --- |
| <span data-ttu-id="1de74-749">(?{code})</span><span class="sxs-lookup"><span data-stu-id="1de74-749">(?{code})</span></span> | <span data-ttu-id="1de74-750">PERL 中的任意 Perl 代码（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-750">arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1de74-751">(??{code})</span><span class="sxs-lookup"><span data-stu-id="1de74-751">(??{code})</span></span> | <span data-ttu-id="1de74-752">PERL 中延迟的任意 Perl 代码（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-752">postponed arbitrary Perl code (NOT SUPPORTED) PERL</span></span> |
| <span data-ttu-id="1de74-753">(?n)</span><span class="sxs-lookup"><span data-stu-id="1de74-753">(?n)</span></span> | <span data-ttu-id="1de74-754">递归调用 regexp 捕获组 n （不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-754">recursive call to regexp capturing group n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-755">(?+n)</span><span class="sxs-lookup"><span data-stu-id="1de74-755">(?+n)</span></span> | <span data-ttu-id="1de74-756">递归调用相对组 +n （不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-756">recursive call to relative group +n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-757">(?-n)</span><span class="sxs-lookup"><span data-stu-id="1de74-757">(?-n)</span></span> | <span data-ttu-id="1de74-758">递归调用相对组 -n （不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-758">recursive call to relative group -n (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-759">(?C)</span><span class="sxs-lookup"><span data-stu-id="1de74-759">(?C)</span></span> | <span data-ttu-id="1de74-760">PCRE 回调（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="1de74-760">PCRE callout (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1de74-761">(?R)</span><span class="sxs-lookup"><span data-stu-id="1de74-761">(?R)</span></span> | <span data-ttu-id="1de74-762">递归调用整个 regexp （等价于 (?0)）（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-762">recursive call to entire regexp (≡ (?0)) (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-763">(?&amp;name)</span><span class="sxs-lookup"><span data-stu-id="1de74-763">(?&amp;name)</span></span> | <span data-ttu-id="1de74-764">递归调用已命名组（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-764">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-765">(?P=name)</span><span class="sxs-lookup"><span data-stu-id="1de74-765">(?P=name)</span></span> | <span data-ttu-id="1de74-766">匹配已命名反向引用（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-766">named backreference (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-767">(?P&gt;name)</span><span class="sxs-lookup"><span data-stu-id="1de74-767">(?P&gt;name)</span></span> | <span data-ttu-id="1de74-768">递归调用已命名组（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-768">recursive call to named group (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-769">(?(cond)true</span><span class="sxs-lookup"><span data-stu-id="1de74-769">(?(cond)true</span></span>|<span data-ttu-id="1de74-770">false)</span><span class="sxs-lookup"><span data-stu-id="1de74-770">false)</span></span> | <span data-ttu-id="1de74-771">条件分支（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-771">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-772">(?(cond)true)</span><span class="sxs-lookup"><span data-stu-id="1de74-772">(?(cond)true)</span></span> | <span data-ttu-id="1de74-773">条件分支（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-773">conditional branch (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-774">(\*ACCEPT)</span><span class="sxs-lookup"><span data-stu-id="1de74-774">(\*ACCEPT)</span></span> | <span data-ttu-id="1de74-775">让 regexps 更类似于 Prolog （不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-775">make regexps more like Prolog (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-776">(\*COMMIT)</span><span class="sxs-lookup"><span data-stu-id="1de74-776">(\*COMMIT)</span></span> | <span data-ttu-id="1de74-777">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-777">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-778">(\*F)</span><span class="sxs-lookup"><span data-stu-id="1de74-778">(\*F)</span></span> | <span data-ttu-id="1de74-779">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-779">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-780">(\*FAIL)</span><span class="sxs-lookup"><span data-stu-id="1de74-780">(\*FAIL)</span></span> | <span data-ttu-id="1de74-781">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-781">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-782">(\*MARK)</span><span class="sxs-lookup"><span data-stu-id="1de74-782">(\*MARK)</span></span> | <span data-ttu-id="1de74-783">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-783">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-784">(\*PRUNE)</span><span class="sxs-lookup"><span data-stu-id="1de74-784">(\*PRUNE)</span></span> | <span data-ttu-id="1de74-785">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-785">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-786">(\*SKIP)</span><span class="sxs-lookup"><span data-stu-id="1de74-786">(\*SKIP)</span></span> | <span data-ttu-id="1de74-787">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-787">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-788">(\*THEN)</span><span class="sxs-lookup"><span data-stu-id="1de74-788">(\*THEN)</span></span> | <span data-ttu-id="1de74-789">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-789">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-790">(\*ANY)</span><span class="sxs-lookup"><span data-stu-id="1de74-790">(\*ANY)</span></span> | <span data-ttu-id="1de74-791">设置换行约定（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-791">set newline convention (NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-792">(\*ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="1de74-792">(\*ANYCRLF)</span></span> | <span data-ttu-id="1de74-793">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-793">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-794">(\*CR)</span><span class="sxs-lookup"><span data-stu-id="1de74-794">(\*CR)</span></span> | <span data-ttu-id="1de74-795">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-795">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-796">(\*CRLF)</span><span class="sxs-lookup"><span data-stu-id="1de74-796">(\*CRLF)</span></span> | <span data-ttu-id="1de74-797">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-797">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-798">(\*LF)</span><span class="sxs-lookup"><span data-stu-id="1de74-798">(\*LF)</span></span> | <span data-ttu-id="1de74-799">（不支持）</span><span class="sxs-lookup"><span data-stu-id="1de74-799">(NOT SUPPORTED)</span></span> |
| <span data-ttu-id="1de74-800">(\*BSR\_ANYCRLF)</span><span class="sxs-lookup"><span data-stu-id="1de74-800">(\*BSR\_ANYCRLF)</span></span> | <span data-ttu-id="1de74-801">设置 \R 约定（不支持） PCRE</span><span class="sxs-lookup"><span data-stu-id="1de74-801">set \R convention (NOT SUPPORTED) PCRE</span></span> |
| <span data-ttu-id="1de74-802">(\*BSR\_UNICODE)</span><span class="sxs-lookup"><span data-stu-id="1de74-802">(\*BSR\_UNICODE)</span></span> | <span data-ttu-id="1de74-803">（不支持）PCRE</span><span class="sxs-lookup"><span data-stu-id="1de74-803">(NOT SUPPORTED) PCRE</span></span> |

## <a name="content-license"></a><span data-ttu-id="1de74-804">内容许可证</span><span class="sxs-lookup"><span data-stu-id="1de74-804">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="1de74-805">本页面的某些部分是根据 Chromium.org 创建和共享的作品所做的修改，并根据 [Creative Commons Attribution 4.0 国际许可证](http://creativecommons.org/licenses/by/4.0/)中所述的条款进行使用。</span><span class="sxs-lookup"><span data-stu-id="1de74-805">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="1de74-806">可在[此处](https://github.com/google/re2/wiki/Syntax)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="1de74-806">The original page can be found [here](https://github.com/google/re2/wiki/Syntax).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="1de74-807">此作品通过 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 国际许可证</a>获得许可。</span><span class="sxs-lookup"><span data-stu-id="1de74-807">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1de74-808">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1de74-808">See also</span></span>

- [<span data-ttu-id="1de74-809">Microsoft Edge Enterprise 登录页面</span><span class="sxs-lookup"><span data-stu-id="1de74-809">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)