#
# Copyright (c) 2016-2017 Vinnie Falco (vinnie dot falco at gmail dot com)
#
# Distributed under the Boost Software License, Version 1.0. (See accompanying
# file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#
# Official repository: https://github.com/boostorg/beast
#

if (OPENSSL_FOUND)
    GroupSources(include/boost/beast beast)
    GroupSources(example/common common)
    GroupSources(example/http/server/stackless-ssl "/")

    add_executable (http-server-stackless-ssl
        ${BOOST_BEAST_INCLUDES}
        ${PROJECT_SOURCE_DIR}/example/common/server_certificate.hpp
        Jamfile
        http_server_stackless_ssl.cpp
    )

    target_link_libraries (http-server-stackless-ssl
        ${OPENSSL_LIBRARIES}
        )

endif()
