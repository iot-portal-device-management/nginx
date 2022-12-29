#
# Copyright (C) 2021-2023 Intel Corporation
# SPDX-License-Identifier: BSD-2-Clause
#

version_settings(constraint='>=0.22.2')

custom_build(
    'iotportaldevicemanagement-nginx',
    'docker build -f Dockerfile.production -t iotportaldevicemanagement-nginx:development .',
    deps=['.', '../api/'],
    tag='development',
    live_update=[
        sync('../api/', '/var/www/html/'),
        sync('./configs/nginx.conf', '/etc/nginx/nginx.conf'),
        sync('./configs/iotportaldevicemanagement.conf', '/etc/nginx/conf.d/iotportaldevicemanagement.conf'),
    ],
    image_deps=['api-builder'],
)