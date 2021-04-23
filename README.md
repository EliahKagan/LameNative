# Ekgn.LameNative (NuGet source)

This repository and NuGet package provide 32-bit and 64-bit native Windows LAME
binaries for encoding MP3 audio (`libmp3lame.dll`). Please see:

- [The LAME Project](https://lame.sourceforge.io) for the upstream project and
  source code, including the source code included here.
- [RareWares | LAME
  Libraries](https://www.rarewares.org/mp3-lame-libraries.php) for
  [downloadable zip archives](https://www.rarewares.org/files/mp3/) containing
  the binaries included here:
  [`libmp3lame-3.99.5x86.zip`](https://www.rarewares.org/files/mp3/libmp3lame-3.99.5x86.zip)
  and
  [`libmp3lame-3.99.5x64.zip`](https://www.rarewares.org/files/mp3/libmp3lame-3.99.5x64.zip).
- [Xycui.LameNative](https://www.nuget.org/packages/Xycui.LameNative), in which
  [Xianyi Cui](https://github.com/xycui) did this first and thus deserves
  credit for the idea.

Neither this package nor its maintainer are affiliated with or endorsed by any
of the above.

The major differences between this and
[Xycui.LameNative](https://www.nuget.org/packages/Xycui.LameNative) are that:

- This package uses the same version numbering scheme as LAME, so you know what
  version you&rsquo;re using when you manage your project&rsquo;s NuGet
  packages.
- I hope to provide updated packages for later versions of the library.
- **This package includes (compressed) source code**&mdash;and even copies it
  to the output directory, too&mdash;to help ease LGPL compliance. (If you
  don&rsquo;t want the source code archive in the output directory, you could
  use a post-build task to remove it.)

Though I obtained the DLLs included here from RareWares (as detailed above),
they are identical to the DLLs in
[Xycui.LameNative](https://www.nuget.org/packages/Xycui.LameNative) (which
perhaps came from there as well). To avoid introducing incompatibility for no
reason, I&rsquo;ve used the same naming convention as in that package (placing
`.32` or `.64` before the `.dll` suffix in each filename, so they can reside in
the same directory).

See the `LICENSE`, `COPYING`, and `README` files, and license headers
(commented license information) on individual source code files, in the
included `.tar.xz` source archive, to verify licensing information and for
details on how to comply with the LGPL. **Please note that the maintainer of
this repository and NuGet package (Eliah Kagan) is not an author or copyright
holder of LAME.** The `.tar.xz` archive is repacked from the upstream `.tar.gz`
file, so it takes up less space when copied to a project&rsquo;s build output
directory as detailed above.

**The contents of this repository, which includes LAME 3.99.5, may be
distributed under the [GNU Lesser General Public License v2.1 or
later](https://spdx.org/licenses/LGPL-2.1-or-later.html).** Some of the files
in LAME show other licenses. In the root of the LAME source tree, the `README`
and `ChangeLog` files offer LAME under the LGPL version 2 or later, and many
files show individual copyright notices that agree with this. But several files
(e.g., `libmp3lame/gain_analysis.c`) say they are licensed under the LGPL 2.1
or later. To be safe, I&rsquo;m offering this repository under those terms. Of
course, all the notices in the LAME source tree are left intact, and nothing
I&rsquo;m saying here should prohibit you from doing anything with LAME that
you would otherwise be allowed to do.

## Installing the NuGet package

In an SDK-style project, run this command to add the NuGet package, obtaining
it from the package source [nuget.org](https://www.nuget.org/):

```powershell
dotnet add package Ekgn.LameNative --version 3.99.5
```

## Building the NuGet package yourself

If you want to build a `.nuget` package file from this repository, run:

```powershell
cd Ekgn.LameNative
nuget pack
```

See [Install NuGet client
tools](https://docs.microsoft.com/en-us/nuget/install-nuget-client-tools#nugetexe-cli)
for instructions on how to install the `nuget` command. If you&rsquo;re on
Windows, another option is to install it with the [`scoop`](https://scoop.sh/)
package manager:

```powershell
scoop install nuget
```

Most likely, you will want to install the package from
[nuget.org](https://www.nuget.org/) rather than building it yourself.

## License Notices

Some copyright and LGPL-related information is reproduced below for
convenience.

LAME&rsquo;s `README` file includes this copyright information:

> Copyrights (c) 1999-2011 by The LAME Project\
> Copyrights (c) 1999,2000,2001 by Mark Taylor\
> Copyrights (c) 1998 by Michael Cheng\
> Copyrights (c) 1995,1996,1997 by Michael Hipp: mpglib
>
> As well as additional copyrights as documented in the source code.

See the full file for more information.

That `README` file also mentions that MPGLIB is released under the GPL.
However, the files present in the `mpglib` directory carry LGPL rather than GPL
license notices (other than `depcomp`, which is an automatically generated file
with a special exception permitting it to be distributed under the terms of a
program that contains it). The [&ldquo;mpglib license in
LAME&rdquo;](https://sourceforge.net/p/lame/mailman/lame-dev/thread/20080724085050.30463yz0cyn01740%40webmail.leidinger.net/#msg19929916)
email thread seems to give some historical insight into this situation.

LGPL 2.1+ file header notice:

> *[copyright and author information]*
>
> This library is free software; you can redistribute it and/or modify it under
the terms of the GNU Lesser General Public License as published by the Free
Software Foundation; either version 2.1 of the License, or (at your option) any
later version.
>
> This library is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE. See the GNU Lesser General Public License for more
details.
>
> You should have received a copy of the GNU Lesser General Public License
along with this library; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA

LGPL 2.0+ file header notice:

> *[copyright and author information]*
>
> This library is free software; you can redistribute it and/or modify it under
the terms of the GNU Library General Public License as published by the Free
Software Foundation; either version 2 of the License, or (at your option) any
later version.
>
> This library is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE.  See the GNU Library General Public License for more
details.
>
> You should have received a copy of the GNU Library General Public License
along with this library; if not, write to the Free Software Foundation, Inc.,
51 Franklin St, Fifth Floor, Boston, MA  02110-1301, USA.

LGPL compliance guidance fom the LAME developers (from the file called
`LICENSE`, also reproduced in the root of this repository as
`COPYING.LAME-HOWTO`):

> Can I use LAME in my commercial program?
>
> Yes, you can, under the restrictions of the LGPL.  The easiest way to do this
is to:
>
> 1. Link to LAME as separate library (libmp3lame.a on unix or lame_enc.dll or
     libmp3lame.dll on windows)
>
> 2. Fully acknowledge that you are using LAME, and give a link to our web
     site, www.mp3dev.org
>
> 3. If you make modifications to LAME, you *must* release these these
     modifications back to the LAME project, under the LGPL.

Note that the official website of The LAME Project has since moved to
https://lame.sourceforge.io.

(See also [Frequently Asked Questions about the GNU
Licenses](https://www.gnu.org/licenses/gpl-faq.en.html) from the Free Software
Foundation.)

## This README, and the .nuspec file, are public domain

This README file, as well as
[`Ekgn.LameNative/Ekgn.LameNative.nuspec`](Ekgn.LameNative/Ekgn.LameNative.nuspec),
were written in 2021 by Eliah Kagan &lt;degeneracypressure@gmail.com&gt;. The
following applies to these two files ONLY:

> To the extent possible under law, the author(s) have dedicated all copyright
and related and neighboring rights to this software to the public domain
worldwide. This software is distributed without any warranty.
>
> You should have received a copy of the CC0 Public Domain Dedication along
with this software. If not, see
&lt;https://creativecommons.org/publicdomain/zero/1.0/&gt;.

The file [`COPYING.CC0`](COPYING.CC0) contains the text of CC0.

This repository as a whole is licensed under the terms of the GNU Lesser
General Public License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version. See
[`COPYING`](COPYING).

(Note: This README file and `Ekgn.LameNative/Ekgn.LameNative.nuspec` may, if
you like, be distributed under the LGPL. But the rest of this repository, which
includes the LAME library from [The LAME
Project](https://lame.sourceforge.io/), MUST NOT be offered under CC0.)
