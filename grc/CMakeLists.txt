# Copyright 2011 Free Software Foundation, Inc.
#
# This file is part of GNU Radio
#
# GNU Radio is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.
#
# GNU Radio is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with GNU Radio; see the file COPYING.  If not, write to
# the Free Software Foundation, Inc., 51 Franklin Street,
# Boston, MA 02110-1301, USA.

install(FILES
    lfast_costas2.xml
    lfast_costas4.xml
    lfast_agc_fast.xml
    lfast_agc_fast_ff.xml
    lfast_CC2F2ByteVector.xml
    lfast_low_pass_filter.xml
    lfast_high_pass_filter.xml
    lfast_root_raised_cosine_filter.xml
    lfast_nlog10volk.xml
    DESTINATION share/gnuradio/grc/blocks
    
)

# lfast_quad_demod_volk.xml 